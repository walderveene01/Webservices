#Tutorial Values

```python
// Nothing to show
```

```json
// Nothing to show
```

```shell
// Nothing to show
```




The following tutorial will show multiple lists. Within the these lists you will see the following Parameter.

Parameter | Value | Description
--------- | ------- | -----------
Eenheden | true/false | This will show the Eenheden.
Grootheden | true/false  | This will show the Grootheden.
Hoedanigheden | true/false  | This will show the Hoedanigheden.
Compartimenten | true/false | This will show the Compartimenten.
Parameters | true/false | This will show the Parameters.

## Imports

```python
import requests
import json
import pandas as pd
```

```json
// Nothing to show
```

```shell
// Nothing to show
```

The following imports are needed to get values from the webservice Metadataservice in python and use this tutorial. 

<aside class="notice">
If you are using the following code you will need all the imports. At the end there will be a version list.
</aside>


## Request 

```python

collect_catalogus = ('https://waterwebservices.rijkswaterstaat.nl/METADATASERVICES_DBO/OphalenCatalogus/')


# get station information from DDL (metadata uit Catalogus)
request = {  
"CatalogusFilter":
	{ 
   	"Grootheden" :True,
    "Parameters":True,
    "Compartimenten":True,
    "Hoedanigheden":True,
    "Eenheden":True,
    "BemonsteringsApparaten" :True,
    "BemonsteringsMethoden":True,
    "BemonsteringsSoorten":True,
    "BioTaxon":True,
    "BioTaxon_Compartimenten":True,
    "MeetApparaten":True,
    "MonsterBewerkingsMethoden":True,
    "Organen":True,
    "PlaatsBepalingsApparaten":True,
    "Typeringen":True,
    "WaardeBepalingstechnieken":True,
    "WaardeBepalingsmethoden":True,
    "WaardeBewerkingsmethoden":True
    }
    
}
```

```json
// Nothing to show check Python
```

```shell
// Nothing to show check Python
```

This code is the request that you send to the webservice

## Response 

```python
resp = requests.post(collect_catalogus, json=request)
result = resp.json()



# print all variables in the catalogus
df_metadata = pd.io.json.json_normalize(result['AquoMetadataLijst']).set_index('AquoMetadata_MessageID')

# Create new frames with all values
df_Compartiment = df_metadata.drop_duplicates(subset=['Compartiment.Code'])
df_Compartiment = df_Compartiment[['Compartiment.Code','Compartiment.Omschrijving']]

df_Parameters = df_metadata.drop_duplicates(subset=['Parameter.Code'])
df_Parameters = df_Parameters[['Parameter.Code','Parameter.Omschrijving']]

df_Eenheden = df_metadata.drop_duplicates(subset=['Eenheid.Code'])
df_Eenheden = df_Eenheden[['Eenheid.Code','Eenheid.Omschrijving']]

df_Grootheden = df_metadata.drop_duplicates(subset=['Grootheid.Code'])
df_Grootheden = df_Grootheden[['Grootheid.Code','Grootheid.Omschrijving']]

df_Hoedanigheden = df_metadata.drop_duplicates(subset=['Hoedanigheid.Code'])
df_Hoedanigheden = df_Hoedanigheden[['Hoedanigheid.Code','Hoedanigheid.Omschrijving']]

df_BemonsteringsApparaten = df_metadata.drop_duplicates(subset=['BemonsteringsApparaat.Code'])
df_BemonsteringsApparaten = df_BemonsteringsApparaten[['BemonsteringsApparaat.Code','BemonsteringsApparaat.Omschrijving']]

df_BemonsteringsMethoden = df_metadata.drop_duplicates(subset=['BemonsteringsMethode.Code'])
df_BemonsteringsMethoden = df_BemonsteringsMethoden[['BemonsteringsMethode.Code','BemonsteringsMethode.Omschrijving']]

df_BemonsteringsSoorten = df_metadata.drop_duplicates(subset=['BemonsteringsSoort.Code'])
df_BemonsteringsSoorten = df_BemonsteringsSoorten[['BemonsteringsSoort.Code','BemonsteringsSoort.Omschrijving']]

df_BioTaxon = df_metadata.drop_duplicates(subset=['BioTaxon.Code'])
df_BioTaxon = df_BioTaxon[['BioTaxon.Code','BioTaxon.Omschrijving']]

df_BioTaxon_Compartimenten = df_metadata.drop_duplicates(subset=['BioTaxon_Compartiment.Code'])
df_BioTaxon_Compartimenten= df_BioTaxon_Compartimenten[['BioTaxon_Compartiment.Code','BioTaxon_Compartiment.Omschrijving']]

df_MeetApparaten = df_metadata.drop_duplicates(subset=['MeetApparaat.Code'])
df_MeetApparaten = df_MeetApparaten[['MeetApparaat.Code','MeetApparaat.Omschrijving']]

df_MonsterBewerkingsMethoden = df_metadata.drop_duplicates(subset=['MonsterBewerkingsMethode.Code'])
df_MonsterBewerkingsMethoden = df_MonsterBewerkingsMethoden[['MonsterBewerkingsMethode.Code','MonsterBewerkingsMethode.Omschrijving']]

df_Organen= df_metadata.drop_duplicates(subset=['Orgaan.Code'])
df_Organen = df_Organen[['Orgaan.Code','Orgaan.Omschrijving']]

df_PlaatsBepalingsApparaten = df_metadata.drop_duplicates(subset=['PlaatsBepalingsApparaat.Code'])
df_PlaatsBepalingsApparaten = df_PlaatsBepalingsApparaten[['PlaatsBepalingsApparaat.Code','PlaatsBepalingsApparaat.Omschrijving']]

df_Typeringen= df_metadata.drop_duplicates(subset=['Typering.Code'])
df_Typeringen= df_Typeringen[['Typering.Code','Typering.Omschrijving']]

df_WaardeBepalingstechnieken= df_metadata.drop_duplicates(subset=['WaardeBepalingstechniek.Code'])
df_WaardeBepalingstechnieken= df_WaardeBepalingstechnieken[['WaardeBepalingstechniek.Code','WaardeBepalingstechniek.Omschrijving']]

df_WaardeBepalingsmethoden= df_metadata.drop_duplicates(subset=['WaardeBepalingsmethode.Code'])
df_WaardeBepalingsmethoden= df_WaardeBepalingsmethoden[['WaardeBepalingsmethode.Code','WaardeBepalingsmethode.Omschrijving']]

df_WaardeBewerkingsmethoden= df_metadata.drop_duplicates(subset=['WaardeBewerkingsmethode.Code'])
df_WaardeBewerkingsmethoden= df_WaardeBewerkingsmethoden[['WaardeBewerkingsmethode.Code','WaardeBewerkingsmethode.Omschrijving']]

# Create a Pandas Excel writer using XlsxWriter as the engine.
writer = pd.ExcelWriter('Values.xlsx', engine='xlsxwriter')

# Convert the dataframe to an XlsxWriter Excel object.
df_Parameters.to_excel(writer, sheet_name='Parameters')
df_Compartiment.to_excel(writer, sheet_name='Compartimenten')
df_Eenheden.to_excel(writer, sheet_name='Eenheden')
df_Hoedanigheden.to_excel(writer, sheet_name='Hoedanigheden')
df_Grootheden.to_excel(writer, sheet_name='Grootheden')
df_BemonsteringsApparaten.to_excel(writer, sheet_name='BemonsteringsApparaten')
df_BemonsteringsMethoden.to_excel(writer, sheet_name='BemonsteringsMethoden')
df_BemonsteringsSoorten.to_excel(writer, sheet_name='BemonsteringsSoorten')
df_BioTaxon.to_excel(writer, sheet_name='BioTaxon')
df_BioTaxon_Compartimenten.to_excel(writer, sheet_name='BioTaxon_Compartimenten')
df_MeetApparaten.to_excel(writer, sheet_name='MeetApparaten')
df_MonsterBewerkingsMethoden.to_excel(writer, sheet_name='MonsterBewerkingsMethoden')
df_Organen.to_excel(writer, sheet_name='Organen')
df_PlaatsBepalingsApparaten.to_excel(writer, sheet_name='PlaatsBepalingsApparaten')
df_Typeringen.to_excel(writer, sheet_name='Typeringen')
df_WaardeBepalingstechnieken.to_excel(writer, sheet_name='WaardeBepalingstechnieken')
df_WaardeBepalingsmethoden.to_excel(writer, sheet_name='WaardeBepalingsmethoden')
df_WaardeBewerkingsmethoden.to_excel(writer, sheet_name='WaardeBewerkingsmethoden')

# Close the Pandas Excel writer and output the Excel file.
writer.save()
```

```json
// Nothing to show check Python
```

```shell
// Nothing to show check Python
```
The following code will take the response and split all the values into 18 different Sheets 

Sheets | Description
--------- | ------| 
| Grootheden | This list Grootheden that can be used in the webservices |
| Parameters | This list Parameters that can be used in the webservices |
| Compartimenten | This list Compartimenten that can be used in the webservices |
| Hoedanigheden | This list Hoedanigheden that can be used in the webservices |
| Eenheden | This list Eenheden that can be used in the webservices |
| BemonsteringsApparaten | This list BemonsteringsApparaten that can be used in the webservices |
| BemonsteringsMethoden | This list BemonsteringsMethoden that can be used in the webservices |
| BemonsteringsSoorten | This list BemonsteringsSoorten that can be used in the webservices |
| BioTaxon | This list BioTaxon that can be used in the webservices |
| BioTaxon_Compartimenten | This list BioTaxon_Compartimenten that can be used in the webservices |
| MeetApparaten | This list MeetApparaten that can be used in the webservices |
| MonsterBewerkingsMethoden | This list MonsterBewerkingsMethoden that can be used in the webservices |
| Organen | This list Organen that can be used in the webservices |
| PlaatsBepalingsApparaten | This list PlaatsBepalingsApparaten that can be used in the webservices |
| Typeringen | This list Typeringen that can be used in the webservices |
| WaardeBepalingstechnieken | This list WaardeBepalingstechnieken that can be used in the webservices |
| WaardeBepalingsmethoden | This list WaardeBepalingsmethoden that can be used in the webservices |
| WaardeBewerkingsmethoden | This list WaardeBewerkingsmethoden that can be used in the webservices |


