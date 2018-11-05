
# Tutorial Locations
```python
//Nothing to show check Python
```

```json
//Nothing to show check Python
```

```shell
//Nothing to show check Python
```
The following code shows step by step how to get a list of Locaties from the Metadatawebservice service. Within the code you get 2 csv-files 

CSV- files | Description
--------- | -----------
true.csv | This will contain all locations with the value true(there is information)
false.csv | This will contain all locations with the value false(there is no information)


## Import
```python
#within python you use the following imports
import requests
import json
import numpy as np
import pandas as pd
from datetime import datetime
import pytz
import objectpath
import time 
import datetime
from time import gmtime, strftime
```

```json
// Nothing to show check Python
```

```shell
// Nothing to show check Python
```

The following imports are needed to get values from the webservice Metadataservice in python.
<aside class="notice">
If you are using the following code you will need all the imports. At the end there will be a version list.
</aside>

## Webservices
```python
#the webservices
collect_catalogus = ('https://waterwebservices.rijkswaterstaat.nl/' +
                     'METADATASERVICES_DBO/' +
                     'OphalenCatalogus/')
collect_observations = ('https://waterwebservices.rijkswaterstaat.nl/' +
                        'ONLINEWAARNEMINGENSERVICES_DBO/' +
                        'OphalenWaarnemingen')
collect_count_observations = ('https://waterwebservices.rijkswaterstaat.nl' +
                              '/ONLINEWAARNEMINGENSERVICES_DBO/CheckWaarnemingenAanwezig')
```


```json
// Nothing to show check Python
```

```shell
// Nothing to show check Python
```

you need 3 different webservices: 

Webservice | 
--------- | 
| OphalenCatalogus |
| OphalenWaarnemingen |
| CheckWaarnemingenAanwezig |


## Request OphalenCatalogus

```python
#The request for ophalencatalogus
request = {
    "CatalogusFilter": {
        "Eenheden": True,
        "Grootheden": True,
        "Hoedanigheden": True,
        "Compartimenten": True,
        "Compartimenten": True
    }
}
```

```json
// Nothing to show check Python
```

```shell
// Nothing to show check Python
```
This is the request you need to define in the code:

Parameter | Value | Description
--------- | ------- | -----------
Eenheden | true/false | This will  show the Eenheden.
Grootheden | true/false  | This will show the Grootheden.
Hoedanigheden | true/false  | This will show the Hoedanigheden.
Compartimenten | true/false | This will show the Compartimenten.
Parameters | true/false | This will show the Parameters.


<aside class="warning">If you want to use the python code described in this documentation you will need to set all the values to true</aside>

## Start/End date

```python
huidige_datum = time.time()

#einddatum word nu de huidige tijd en datum ingevoerd. 
#Je kan ook je eigen datum en tijd invoeren comment deze 3 regels dan uit.
eind_datum = datetime.datetime.fromtimestamp(huidige_datum).strftime('%Y-%m-%dT%H:%M:%S')
eind_datum = pd.to_datetime(eind_datum) - pd.DateOffset(days=29)
eind_datum = str(eind_datum).replace(" ","T")+".000+01:00"

#deze is op het jaar 1900 neergezet om te kijken of er ooit gegevens zijn toegevoegt. 
#Je kan ook je eigen datums invullen gebruik wel dit format
begin_datum ="1900-01-01T00:00:00.000+01:00"

#de code voor het compartiment.
Code_compartiment = "OW"

#de code voor de eenheid.
Code_eenheid = "cm"

#hier word de lege dataframe df_locatie aangemaakt.
columns = ['Code','true/false']

df_locatie = pd.DataFrame( columns=columns)
```

```json
// Nothing to show check Python
```

```shell
// Nothing to show check Python
```

Within the request for checkaanwezigwaarnemingen you need to set the following values:

Parameter | Value | Description
--------- | ------- | -----------
eind_datum | 0000-00-00T00:00:00.000+01:00 | This is the format to define the date and time
Begin_datum | 0000-00-00T00:00:00.000+01:00 | This is the format to define the date and time
Compartimenten |  <a href='/?python#tutorial-values'>make your own list using Tutorial Values </a> | This will show the Compartimenten.
Eenheden | <a href='/?python#tutorial-values'>make your own list using Tutorial Values </a> | This will  show the Eenheden.

<aside class="warning">for the start and end date you need to use <code>0000-00-00T00:00:00.000+01:00</code> as format</aside>

## Transform JSON response

```python
#hier word de locatie lijst gepulled van de api en in een json format opgeslagen.
resp = requests.post(collect_catalogus, json=request)
result = resp.json()

# hier word dataframe df_locaties aangemaakt.
df_locations = pd.DataFrame(result['LocatieLijst'])
```

```json
// Nothing to show check Python
```

```shell
// Nothing to show check Python
```

The following code transforms the json response to an dataframe.

## Check information
```python
#voor elke regel in het dataframe df_locations 
for index, row in df_locations.iterrows():
#haal de x waarde op
    x = getattr(row, "X")
    
#haal de y waarde op 
    y = getattr(row, "Y")

#haal de locatie code op 
    locatie= getattr(row, "Code")

#Hier word de request aangemaakt. alle variabele worden automatisch ingevoerd. 
    request_aantal = {
        "AquoMetadataLijst" :[{"Compartiment":{"Code":Code_compartiment},
        "Eenheid":{"Code":Code_eenheid}}],
        "LocatieLijst" : [{"X" :x,"Y":y,"Code":locatie}],
        "Periode" : {"Begindatumtijd" : begin_datum,"Einddatumtijd": eind_datum}
    }
```

```json
// Nothing to show check Python
```

```shell
// Nothing to show check Python
```
To check if a location has information you need to send a new request to checkaanwezigheidwaarneming. The code will do it every location in a for loop.

Parameter | Value | Description
--------- | ------- | -----------
eind_datum | 0000-00-00T00:00:00.000+01:00 | This is the format to define the date and time
Begin_datum | 0000-00-00T00:00:00.000+01:00 | This is the format to define the date and time
Compartimenten |  <a href='/?python#tutorial-values'>make your own list using Tutorial Values </a> | This will show the Compartimenten.
Eenheden | <a href='/?python#tutorial-values'>make your own list using Tutorial Values </a> | This will  show the Eenheden.


## Response to dataframe

```python
#hier word een nieuwe statement uitgevoerd op check aantal waarnemingen 
#om te kijken of de request een response geeft met waardes
    resp = requests.post(collect_count_observations, json=request_aantal)
    result_aantal = resp.json()

#hier word in het resultaat gezocht naar het object waarnemingen aanwezig
    jsonnn_tree = objectpath.Tree(result_aantal)
    resultaat =  tuple(jsonnn_tree.execute('$..WaarnemingenAanwezig'))
    resultaat = resultaat[0]

#als de waarde van de api true is 
    if resultaat == "true":
        lijst = pd.DataFrame([[locatie,resultaat]], columns=('Code','true/false'))
        df_locatie = df_locatie.append(lijst)

#als de waarde van de api false is 
    elif resultaat == "false":
        lijst = pd.DataFrame([[locatie,resultaat]], columns=('Code','true/false'))
        df_locatie = df_locatie.append(lijst)
```

```json
// Nothing to show check Python
```

```shell
// Nothing to show check Python
```
within the forloop you need to check if there are values. The response and the location wil be send to the right dataframe 

Table | Description
--------- | -----------
true.csv | This will contain all locations with the value true(there is information)
false.csv | This will contain all locations with the value false(there is no information)

## Dataframe to csv

```python
#de waarde van resultaat en de code an de locatie word vervolgens toevegoegd 
#aan een nieuwe dataframe ofwel de true ofwel de false
df_true = df_locatie.loc[df_locatie['true/false'] == "true"]
df_false = df_locatie.loc[df_locatie[ 'true/false'] == "false"]

# Zowel voor true als voor false word een csv bestand aangemaakt 
#en worden de gegevens weggeschreven.

# Create a Pandas Excel writer using XlsxWriter as the engine.
writer = pd.ExcelWriter('true.xlsx', engine='xlsxwriter')

# Convert the dataframe to an XlsxWriter Excel object.
df_true.to_excel(writer, sheet_name='Sheet1')

# Close the Pandas Excel writer and output the Excel file.
writer.save()

writer = pd.ExcelWriter('false.xlsx', engine='xlsxwriter')

# Convert the dataframe to an XlsxWriter Excel object.
df_false.to_excel(writer, sheet_name='Sheet1')

# Close the Pandas Excel writer and output the Excel file.
writer.save()
```



```json
// Nothing to show check Python
```

```shell
// Nothing to show check Python 
```

This will send all your dataframes wich you created to 2 different csv files

Table | Description
--------- | -----------
true.csv | This will contain all locations with the value true(there is information)
false.csv | This will contain all locations with the value false(there is no information)

<aside class="notice">
You can change the name of the files 
</aside>
