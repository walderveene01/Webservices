# OnlineWaarnemingenservice
The Onlinewaarnemingen unlocks the distribution layer observations. Based on the request
there observations and information about the number of observations collected and built up.

 Operations | 
| ----- |
| OphalenWaarnemingen | 
| OphalenLaatsteWaarnemingen | 
| OphalenAantalWaarnemingen | 
|  CheckWaarnemingenAanwezig.


## OphalenWaarnemingen 

```python 
// Nothing to show check JSON
```

```json
{"AquoPlusWaarnemingMetadata":
    {"AquoMetadata":{"Compartiment":{"Code":"VALUE"},
        "Eenheid":{"Code":"VALUE"},
        "MeetApparaat":{"Code":"VALUE"},
        "Grootheid":{"Code":"VALUE"}}},
        "Locatie":{"X":VALUE,"Y":VALUE,"Code":"VALUE"},
        "Periode":{"Begindatumtijd":"VALUE","Einddatumtijd":"VALUE"}
    }
} 
```
```shell
{"WaarnemingenLijst":[
{"Locatie":{"Locatie_MessageID":VALUE,"Coordinatenstelsel":"25831","X":VALUE,"Y":VALUE,
    "Naam":"VALUE","Code":"VALUE"},
    "MetingenLijst":[{"Tijdstip":"VALUE",
    "Meetwaarde":{"Waarde_Numeriek":VALUE},
    "WaarnemingMetadata":{"StatuswaardeLijst":["VALUE"],
    "BemonsteringshoogteLijst":["VALUE"],
    "ReferentievlakLijst":["VALUE"],
    "OpdrachtgevendeInstantieLijst":["VALUE"],
    "KwaliteitswaardecodeLijst":["VALUE"]}}],
    "AquoMetadata":{"AquoMetadata_MessageID":VALUE,
    "Parameter_Wat_Omschrijving":"VALUE",
    "BemonsteringsApparaat":{"Code":"VALUE","Omschrijving": "VALUE"},
    "BemonsteringsMethode":{"Code":"VALUE","Omschrijving":"VALUE"},
    "BemonsteringsSoort":{"Code":"VALUE","Omschrijving":"VALUE"},
    "BioTaxon":{"Code":"VALUE","Omschrijving":"VALUE"},
    "BioTaxon_Compartiment":{"Code":"VALUE","Omschrijving":"VALUE"},
    "Compartiment":{"Code":"VALUE","Omschrijving":"Oppervlaktewater"},
    "Eenheid":{"Code":"VALUE","Omschrijving":"VALUE"},
    "Grootheid":{"Code":"VALUE","Omschrijving":"VALUE"},
    "Hoedanigheid":{"Code":"VALUE","Omschrijving":"VALUE"},
    "MeetApparaat":{"Code":"VALUE","Omschrijving":"VALUE"},
    "MonsterBewerkingsMethode":{"Code":"VALUE","Omschrijving":"VALUE"},
    "Orgaan":{"Code":"VALUE","Omschrijving":"VALUE"},
    "Parameter":{"Code":"VALUE","Omschrijving":"VALUE"},
    "PlaatsBepalingsApparaat":{"Code":"VALUE","Omschrijving":"VALUE"},
    "Typering":{"Code":"VALUE","Omschrijving":"VALUE"},
    "WaardeBepalingstechniek":{"Code":"VALUE","Omschrijving":"VALUE"},
    "WaardeBepalingsmethode":{"Code":"other:VALUE","Omschrijving":"VALUE"},
    "WaardeBewerkingsmethode":{"Code":"VALUE","Omschrijving":"VALUE"}
            }
        }
    ],
    "Succesvol":VALUE
    }
```
A sample request for retrieving observations in a certain period, which
meet the specified aquometadata, locations (s) and observation metadata.

Methode | Content-Type | URL
--------- | ----------- | -----------
POST | application/json | https://waterwebservices.rijkswaterstaat.nl/ONLINEWAARNEMINGENSERVICES_DBO/OphalenWaarnemingen



Attribute | Value | Description
--------- | ------- | -----------
Eenheden | <a href='/?python#tutorial-values'>List using Tutorial Values </a> | This will  show the Eenheden.
Grootheden | <a href='/?python#tutorial-values'>List using Tutorial Values </a> | This will show the Grootheden.
Hoedanigheden | <a href='/?python#tutorial-values'>List using Tutorial Values </a> | This will show the Hoedanigheden.
Compartimenten |  <a href='/?python#tutorial-values'>List using Tutorial Values </a> | This will show the Compartimenten.
Parameters |  <a href='/?python#tutorial-values'>List using Tutorial Values </a>  | This will show the Parameters.
| Meetapparaten |  <a href='/?python#tutorial-values'>List using Tutorial Values </a>  | This list Meetapparaten that can be used in the webservices |
Locatie | <a href='/?python#tutorial-locations'>List using Tutorial locations </a>  | This will show the locations with and without data.
Periode | 0000-00-00T00:00:00.000+01:00 | Time in the format 


## OphalenLaatsteWaarnemingen
```python
//Nothing to show check JSON
```
```json
{"AquoPlusWaarnemingMetadataLijst":
    [
        {"AquoMetadata":{"Compartiment":{"Code":"VALUE"},"Eenheid":{"Code":"VALUE"},
        "Grootheid":{"Code":"VALUE"}}}],
        "LocatieLijst":[{"X":VALUE,"Y":VALUE,"Code":"VALUE"
        }
    ]
}
```

```shell
{"WaarnemingenLijst":[
{"Locatie":{"Locatie_MessageID":VALUE,"Coordinatenstelsel":"25831","X":VALUE,"Y":VALUE,"Naam":"VALUE","Code":"VALUE"},
    "MetingenLijst":[{"Tijdstip":"VALUE",
    "Meetwaarde":{"Waarde_Numeriek":VALUE},
    "WaarnemingMetadata":{"StatuswaardeLijst":["VALUE"],
    "BemonsteringshoogteLijst":["VALUE"],
    "ReferentievlakLijst":["VALUE"],"OpdrachtgevendeInstantieLijst":["VALUE"],
    "KwaliteitswaardecodeLijst":["VALUE"]}}],
    "AquoMetadata":{
    "AquoMetadata_MessageID":VALUE,
    "Parameter_Wat_Omschrijving":"VALUE",
    "BemonsteringsApparaat":{"Code":"VALUE","Omschrijving":"VALUE"},
    "BemonsteringsMethode":{"Code":"VALUE","Omschrijving":"VALUE"},
    "BemonsteringsSoort":{"Code":"01","Omschrijving":"Rechtstreekse meting"},
    "BioTaxon":{"Code":"VALUE","Omschrijving":"VALUE"},
    "BioTaxon_Compartiment":{"Code":"VALUE","Omschrijving":"VALUE"},
    "Compartiment":{"Code":"VALUE","Omschrijving":"VALUE"},
    "Eenheid":{"Code":"VALUE","Omschrijving":"VALUE"},
    "Grootheid":{"Code":"VALUE","Omschrijving":"VALUE"},
    "Hoedanigheid":{"Code":"VALUE","Omschrijving":"VALUE"},
    "MeetApparaat":{"Code":"VALUE","Omschrijving":"VALUE"},
    "MonsterBewerkingsMethode":{"Code":"VALUE","Omschrijving":"VALUE"},
    "Orgaan":{"Code":"VALUE","Omschrijving":"VALUE"},
    "Parameter":{"Code":"VALUE","Omschrijving":"VALUE"},
    "PlaatsBepalingsApparaat":{"Code":"VALUE","Omschrijving":"VALUE"},
    "Typering":{"Code":"VALUE","Omschrijving":"VALUE"},
    "WaardeBepalingstechniek":{"Code":"VALUE","Omschrijving":"VALUE"},
    "WaardeBepalingsmethode":{"Code":"other:F046","Omschrijving":"Freq/tijd analyse energie en richtingen, methode CIC/GLFPAR"},
    "WaardeBewerkingsmethode":{"Code":"VALUE","Omschrijving":"VALUE"}}},
    {"Locatie":{"Locatie_MessageID":VALUE,"Coordinatenstelsel":"25831","X":VALUE,"Y":VALUE,"Naam":" VALUE","Code":"VALUE"},
    "MetingenLijst":[{"Tijdstip":"VALUE",
    "Meetwaarde":{"Waarde_Numeriek":VALUE},
    "WaarnemingMetadata":{
    "StatuswaardeLijst":["VALUE"],
    "BemonsteringshoogteLijst":["VALUE"],
    "ReferentievlakLijst":["VALUE"],
    "OpdrachtgevendeInstantieLijst":["VALUE"],
    "KwaliteitswaardecodeLijst":["VALUE"]}}],
    "AquoMetadata":{
        "AquoMetadata_MessageID":VALUE,
        "Parameter_Wat_Omschrijving":"VALUE",
        "BemonsteringsApparaat":{"Code":"VALUE","Omschrijving":"VALUE"},
        "BemonsteringsMethode":{"Code":"VALUE","Omschrijving":"VALUE"},
        "BemonsteringsSoort":{"Code":"VALUE","Omschrijving":"VALUE"},
        "BioTaxon":{"Code":"VALUE","Omschrijving":"VALUE"},
        "BioTaxon_Compartiment":{"Code":"VALUE","Omschrijving" :"VALUE"},
        "Compartiment":{"Code":"VALUE","VALUE"},
        "Eenheid":{"Code":"VALUE","Omschrijving":"VALUE"},
        "Grootheid":{"Code":"VALUE","Omschrijving":"VALUE"},
        "Hoedanigheid":{"Code":"VALUE","Omschrijving":"VALUE"},
        "MeetApparaat":{"Code":"VALUE","Omschrijving":"VALUE"},
        "MonsterBewerkingsMethode":{"Code":"VALUE"," VALUE":"VALUE"},
        "Orgaan":{"Code":"VALUE","Omschrijving":"VALUE"},
        "Parameter":{"Code":"VALUE","Omschrijving":"VALUE"},
        "PlaatsBepalingsApparaat":{"Code":"VALUE","Omschrijving":"VALUE"},
        "Typering":{"Code":"VALUE","Omschrijving":"VALUE"},
        "WaardeBepalingstechniek":{"Code":"VALUE","Omschrijving":"VALUE"},
        "WaardeBepalingsmethode":{"Code":"other:VALUE","Omschrijving":"VALUE"},
        "WaardeBewerkingsmethode":{"Code":"VALUE","Omschrijving":"VALUE"}
        }
    }
],
    "Succesvol":VALUE
}
```


The following is a sample request for retrieving the last observation that satisfy the
specified aquometadata, locations (s) and observation metadata.

Methode | Content-Type | URL
--------- | ----------- | -----------
POST | application/json | https://waterwebservices.rijkswaterstaat.nl/ONLINEWAARNEMINGENSERVICES_DBO/OphalenLaatsteWaarnemingen

Attribute | Description | Value
--------- | ----------- | --------- 
| Compartimenten |  <a href='/?python#tutorial-values'>make your own list using Tutorial Values </a>  | This list Compartimenten that can be used in the webservices |
| Eenheden |  <a href='/?python#tutorial-values'>make your own list using Tutorial Values </a>  | This list Eenheden that can be used in the webservices |
| Grootheden |  <a href='/?python#tutorial-values'>make your own list using Tutorial Values </a>  | This list Grootheden that can be used in the webservices |
LocatieLijst | Vul dit later aan | vul dit later aan


## CheckWaarnemingen Aanwezig

```python
//Nothing to show check JSON
```

```json
{"AquoMetadataLijst" :
    [{
        "Compartiment":{"Code":"VALUE"},"Eenheid":{"Code":"VALUE"}}],
        "LocatieLijst" : [{"X" :VALUE,"Y" :VALUE,"Code":"VALUE"}],
        "Periode" : {
                "Begindatumtijd" : "VALUE",
                "Einddatumtijd" : "VALUE"
                }
        }
```

```shell
{
    "Succesvol":true,
    "WaarnemingenAanwezig":"true"
    }

When there are no Values:
{
    "Succesvol":true,
    "WaarnemingenAanwezig":"false"
}


```

Below is a sample request for checking if there are observations for one
certain period that meet the specified aquometadata, locations (s) and observation metadata.

Methode | Content-Type | URL
--------- | ----------- | -----------
POST | application/json | https://waterwebservices.rijkswaterstaat.nl/ONLINEWAARNEMINGENSERVICES_DBO/CheckWaarnemingen


Atrribute | Value | Description
--------- | ----------- | --------- 
| Compartimenten |  <a href='/?python#tutorial-values'>make your own list using Tutorial Values </a>  | This list Compartimenten that can be used in the webservices |
| Eenheden |  <a href='/?python#tutorial-values'>make your own list using Tutorial Values </a>  | This list Eenheden that can be used in the webservices |
Periode | 0000-00-00T00:00:00.000+01:00 | Time in the format 
LocatieLijst | Vul dit later aan | vul dit later aan

## OphalenAantalWaarnemingen

```python
//Nothing to show Check JSON
```
```json
{"AquoMetadataLijst" :
    [{
    "Compartiment":{"Code":"VALUE"},
    "Eenheid":{"Code":"VALUE"}}],
    "Groeperingsperiode" : "VALUE",
    "LocatieLijst" : [{
        "X" :VALUE,
        "Y" :VALUE,
        "Code":"VALUE"}],
    "Periode" : {
        "Begindatumtijd" : "VALUE",
        "Einddatumtijd": "VALUE"}}
```

```shell 
{"AantalWaarnemingenPerPeriodeLijst":[
    {"AquoMetadata":{"AquoMetadata_MessageID":VALUE,
        "Parameter_Wat_Omschrijving":"VALUE",
        "BemonsteringsApparaat":{"Code":"VALUE","Omschrijving":"VALUE"},
        "BemonsteringsMethode":{"Code":"VALUE","Omschrijving":"VALUE"},
        "BemonsteringsSoort":{"Code":"VALUE","Omschrijving":"VALUE"},
        "BioTaxon":{"Code":"VALUE","Omschrijving":"VALUE"},
        "BioTaxon_Compartiment":{"Code":"VALUE","Omschrijving":"VALUE"},
        "Compartiment":{"Code":"VALUE","Omschrijving":"VALUE"},
        "Eenheid":{"Code":"VALUE","Omschrijving":"VALUE"},
        "Grootheid":{"Code":"VALUE","Omschrijving":"VALUE"},
        "Hoedanigheid":{"Code":"VALUE","Omschrijving":"VALUE"},
        "MeetApparaat":{"Code":"VALUE","Omschrijving":"VALUE"},
        "MonsterBewerkingsMethode":{"Code":"VALUE","Omschrijving":"VALUE"},
        "Orgaan":{"Code":"VALUE","Omschrijving":"VALUE"},
        "Parameter":{"Code":"VALUE","Omschrijving":"VALUE"},
        "PlaatsBepalingsApparaat":{"Code":"VALUE","Omschrijving":"VALUE"},
        "Typering":{"Code":"VALUE","Omschrijving":"VALUE"},
        "WaardeBepalingstechniek":{"Code":"VALUE","Omschrijving ":"VALUE"},
        "WaardeBepalingsmethode":{"Code":"VALUE","Omschrijving":"VALUE"},
        "WaardeBewerkingsmethode":{"Code":"VALUE","Omschrijving":"VALUE"}},
        "Locatie":{"Locatie_MessageID":VALUE,"Coordinatenstelsel":"VALUE","X":VALUE,"Y":VALUE,"Naam":" VALUE","Code":"VALUE"},
        "AantalMetingenPerPeriodeLijst":[{"Groeperingsperiode":{"Jaarnummer":VALUE,"Week":VALUE},"AantalMetingen":VALUE}]},
```

The following is an example request for retrieving the number of observations about a certain one
period that met the specified aquometadata, locations (locations) and perception metadata, grouped
over a certain grouping period. NB: this web service is not used yet and there are
performance problems known.

Methode | Content-Type | URL
--------- | ----------- | -----------
POST | application/json | https://waterwebservices.rijkswaterstaat.nl/ONLINEWAARNEMINGENSERVICES_DBO/OphalenAantalWaarnemingen


Attribute | Value | Description
--------- | ----------- | --------- 
| Compartimenten |  <a href='/?python#tutorial-values'>make your own list using Tutorial Values </a>  | This list Compartimenten that can be used in the webservices |
| Eenheden |  <a href='/?python#tutorial-values'>make your own list using Tutorial Values </a>  | This list Eenheden that can be used in the webservices |
Periode | 0000-00-00T00:00:00.000+01:00 | Time in the format 
LocatieLijst | Vul dit later aan | vul dit later aan

