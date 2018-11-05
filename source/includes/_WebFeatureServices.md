# WebFeatureServices

There are two available WFS features for the distribution layer:

| Function | 
| ------ |
|  Locaties | 
| LocatiesMetLaatsteWaarneming

## Locaties

```python
//Nothing to show Check JSON
```

```json
<wfs:GetFeature
    xmlns:wfs="http://www.opengis.net/wfs"
    service="WFS" version="1.1.0"
    outputFormat="GML3"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.opengis.net/wfshttp://schemas.opengis.net/wfs/1.1.0/wfs.xsd">
    <wfs:QueryTypeName="feature:locaties"
    srsName="EPSG:25831"
    xmlns:feature="http://mapserver.gis.umn.edu/mapserver">
    </wfs:Query></wfs:GetFeature>
```

```shell
    <?xml version='1.0' encoding="ISO-8859-1" ?>
    <wfs:FeatureCollection xmlns:ms="http://mapserver.gis.umn.edu/mapserver"
    xmlns:gml="http://www.opengis.net/gml"
    xmlns:wfs="http://www.opengis.net/wfs"
    xmlns:ogc="http://www.opengis.net/ogc"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://mapserver.gis.umn.edu/mapserver
    http://test.intranet.rijkswaterstaat.nl/services/geoservicesupdate/distributielaag_waterportaal?SERVICE=WFS&amp;VERSION=1.1.0&
    amp;REQUEST=DescribeFeatureType&amp;TYPENAME=feature:locaties&amp;OUTPUTFORMAT=SFE_XMLSCHEMA http://www.opengis.net/wfs http://schemas.opengis.net/wfs/1.1.0/wfs.xsd">
    <gml:boundedBy>
    <gml:Envelope srsName="EPSG:25831">
    <gml:lowerCorner>595875.376191 5790952.822103</gml:lowerCorner>
    <gml:upperCorner>595875.376191 5790952.822103</gml:upperCorner>
    </gml:Envelope>
    </gml:boundedBy>
    <gml:featureMember>
    <ms:locaties gml:id="locaties.195068918">
    <gml:boundedBy>
    <gml:Envelope srsName="EPSG:25831">
    <gml:lowerCorner>595875.376191 5790952.822103</gml:lowerCorner>
    <gml:upperCorner>595875.376191 5790952.822103</gml:upperCorner>
    </gml:Envelope>
    </gml:boundedBy>
    <ms:msGeometry>
    <gml:Point srsName="EPSG:25831">
    <gml:pos>595875.376191 5790952.822103</gml:pos>
    </gml:Point>
    </ms:msGeometry>
    <ms:LOCATIE_MESSAGEID>195068918</ms:LOCATIE_MESSAGEID>
    <ms:NAAM>Noordwijk 2 km uit de kust</ms:NAAM>
    <ms:CODE>NOORDWK2</ms:CODE>
    <ms:OMSCHRIJVING></ms:OMSCHRIJVING>
    <ms:BEMONSTERINGSAPPARAATCODE>70</ms:BEMONSTERINGSAP
    PARAATCODE>
    <ms:BEMONSTERINGSMETHODECODE>NVT</ms:BEMONSTERINGS
    METHODECODE>
    <ms:BEMONSTERINGSSOORTCODE>02</ms:BEMONSTERINGSSOORTCODE>
    <ms:BIOTAXONCODE>NVT</ms:BIOTAXONCODE>
    <ms:BIOTAXON_COMPARTIMENTCODE>NVT</ms:BIOTAXON_COMPARTIMENTCODE>
    <ms:COMPARTIMENTCODE>OW</ms:COMPARTIMENTCODE>
    <ms:EENHEIDCODE>mg/l</ms:EENHEIDCODE>
    <ms:GROOTHEIDCODE>NVT</ms:GROOTHEIDCODE>
    <ms:HOEDANIGHEIDCODE>NVT</ms:HOEDANIGHEIDCODE>
    <ms:MEETAPPARAATCODE>NVT</ms:MEETAPPARAATCODE>
    <ms:MONSTERBEWERKINGSMETHODECODE>NVT</ms:MONSTERBEWERKINGSMETHODECODE>
    <ms:ORGAANCODE>NVT</ms:ORGAANCODE>
    <ms:PARAMETERCODE>O2</ms:PARAMETERCODE>
    <ms:PLAATSBEPALINGSAPPARAATCODE>NVT</ms:PLAATSBEPALINGSAPPARAATCODE>
    <ms:TYPERINGCODE>NVT</ms:TYPERINGCODE>
    <ms:WAARDEBEPALINGSTECHNIEKCODE>NVT</ms:WAARDEBEPALINGSTECHNIEKCODE>
    <ms:WAARDEBEPALINGSMETHODECODE>ZINTUIGLIJK</ms:WAARDEBEPALINGSMETHODECODE>
    <ms:WAARDEBEWERKINGSMETHODECODE>NVT</ms:WAARDEBEWERKINGSMETHODECODE>
    </ms:locaties>
    </gml:featureMember>
    </wfs:FeatureCollection>
```

Below is a sample request for calling the Locations WFS. In the message body of
the POST request one can build a filter to get the desired result.


Methode | Content-Type | URL
--------- | ----------- | -----------
POST | application/json | https://waterwebservices.rijkswaterstaat.nl/services/distributielaagWFS/distributielaag_dbo?SERVICE=WFS&VER
SION=1.1.0&REQUEST=GetCapabilities


Attribute | Value | Description
--------- | ----------- | --------- 
| Grootheden |  <a href='/?python#tutorial-values'>make your own list using Tutorial Values </a>  | This list Grootheden that can be used in the webservices |
| Eenheden |  <a href='/?python#tutorial-values'>make your own list using Tutorial Values </a>  | This list Eenheden that can be used in the webservices |
| Compartimenten |  <a href='/?python#tutorial-values'>make your own list using Tutorial Values </a>  | This list Compartimenten that can be used in the webservices |
LocatieLijst | Vul dit later aan | vul dit later aan


## LocatiesMetLaatsteWaarneming




```python
//Nothing to show Check JSON
```

```json
    <wfs:GetFeature
    xmlns:wfs="http://www.opengis.net/wfs"
    service="WFS" version="1.1.0"
    outputFormat="GML3"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.opengis.net/wfshttp://schemas.opengis.net/wfs/1.1.0/wfs.xsd"><wfs:Query
    typeName="feature:locatiesmetlaatstewaarneming" srsName="EPSG:25831"
    xmlns:feature="http://mapserver.gis.umn.edu/mapserver">
    </wfs:Query>
    </wfs:GetFeature>
```
```shell
    <?xml version='1.0' encoding="ISO-8859-1" ?>
    <wfs:FeatureCollection xmlns:ms="http://mapserver.gis.umn.edu/mapserver"
    xmlns:gml="http://www.opengis.net/gml"
    xmlns:wfs="http://www.opengis.net/wfs"
    xmlns:ogc="http://www.opengis.net/ogc"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://mapserver.gis.umn.edu/mapserverhttp://test.intranet.rijkswaterstaat.nl/services/geoservicesupdate/distributielaag_waterportaal?SERVICE=WFS&amp;VERSION=1.1.0&amp;REQUEST=DescribeFeatureType&ampTYPENAME=feature:locatiesmetlaatstewaarneming&amp;OUTPUTFORMAT=SFE_XMLSCHEMA
    http://www.opengis.net/wfs http://schemas.opengis.net/wfs/1.1.0/wfs.xsd">
    <gml:boundedBy>
    <gml:Envelope srsName="EPSG:25831">
    <gml:lowerCorner>518882.333320 5760829.117296</gml:lowerCorner>
    <gml:upperCorner>518882.333320 5760829.117296</gml:upperCorner>
    </gml:Envelope>
    </gml:boundedBy>
    <gml:featureMember>
    <ms:locatiesmetlaatstewaarneming
    gml:id="locatiesmetlaatstewaarneming.195068918">
    <gml:boundedBy>
    <gml:Envelope srsName="EPSG:25831">
    <gml:lowerCorner>518882.333320 5760829.117296</gml:lowerCorner>
    <gml:upperCorner>518882.333320 5760829.117296</gml:upperCorner>
    </gml:Envelope>
    </gml:boundedBy>
    <ms:msGeometry>
    <gml:Point srsName="EPSG:25831">
    <gml:pos>518882.333320 5760829.117296</gml:pos>
    </gml:Point>
    </ms:msGeometry>
    <ms:WAARNEMING_ID>195068918</ms:WAARNEMING_ID>
    <ms:NAAM>Euro platform</ms:NAAM>
    <ms:CODE>EURPFM</ms:CODE>
    <ms:OMSCHRIJVING></ms:OMSCHRIJVING>
    <ms:STATUSWAARDE>Ongecontroleerd</ms:STATUSWAARDE>
    <ms:BEMONSTERINGSHOOGTE>-100</ms:BEMONSTERINGSHOOGTE>
    <ms:REFERENTIEVLAK>NVT</ms:REFERENTIEVLAK>
    <ms:OPDRACHTGEVENDE_INSTANTIE>RIKZMON_GOLVEN</ms:OPDRACHTGEVENDE_INSTANTIE>
    <ms:KWALITEITSWAARDE_CODE>00</ms:KWALITEITSWAARDE_CODE>
    <ms:WAARDE_LAATSTE_METING>230</ms:WAARDE_LAATSTE_METING>
    <ms:TIJDSTIP_LAATSTE_METING>2013-01-31T23:50:00.000+01:00</ms:TIJDSTIP_LAATSTE_METING>
    <ms:PARAMETER_WAT_OMSCHRIJVING>Gemiddelde golfhoogte uithoogste 1/3 deel van de golven Oppervlaktewatercm</ms:PARAMETER_WAT_OMSCHRIJVING>
    <ms:BEMONSTERINGSAPPARAATCODE>NVT</ms:BEMONSTERINGSAPPARAATCODE>
    <ms:BEMONSTERINGSMETHODECODE>NVT</ms:BEMONSTERINGSMETHODECODE>
    <ms:BEMONSTERINGSSOORTCODE>01</ms:BEMONSTERINGSSOORTCODE>
    <ms:BIOTAXONCODE>NVT</ms:BIOTAXONCODE>
    <ms:BIOTAXON_COMPARTIMENTCODE>NVT</ms:BIOTAXON_COMPARTIMENTCODE>
    <ms:COMPARTIMENTCODE>OW</ms:COMPARTIMENTCODE>
    <ms:EENHEIDCODE>cm</ms:EENHEIDCODE>
    <ms:GROOTHEIDCODE>H1/3</ms:GROOTHEIDCODE>
    <ms:HOEDANIGHEIDCODE>NVT</ms:HOEDANIGHEIDCODE>
    <ms:MEETAPPARAATCODE>109</ms:MEETAPPARAATCODE>
    <ms:MONSTERBEWERKINGSMETHODECODE>NVT</ms:MONSTERBEWERKINGSMETHODECODE>
    <ms:ORGAANCODE>NVT</ms:ORGAANCODE>
    <ms:PARAMETERCODE>NVT</ms:PARAMETERCODE>
    <ms:PLAATSBEPALINGSAPPARAATCODE>NVT</ms:PLAATSBEPALINGSAPPARAATCODE>
    <ms:TYPERINGCODE>NVT</ms:TYPERINGCODE>
    <ms:WAARDEBEPALINGSTECHNIEKCODE>NVT</ms:WAARDEBEPALINGSTECHNIEKCODE>
    <ms:WAARDEBEPALINGSMETHODECODE>other:F046</ms:WAARDEBEPALINGSMETHODECODE>
    <ms:WAARDEBEWERKINGSMETHODECODE>NVT</ms:WAARDEBEWERKINGSMETHODECODE>
    </ms:locatiesmetlaatstewaarneming>
    </gml:featureMember>
    </wfs:FeatureCollection>
```


The following is a sample request for calling the Locations with the Release WFS. In
the message body of the POST request one can build a filter in order to obtain the desired resultask.

Methode | Content-Type | URL
--------- | ----------- | -----------
POST | application/json | https://waterwebservices.rijkswaterstaat.nl/services/distributielaagWFS/distributielaag_dbo?SERVICE=WFS&VERSION=1.1.0&REQUEST=GetFeature&TYPENAME=locatiesmetlaatstewaarneming&Maxfeatures=50


Attribute | Value | Description
--------- | ----------- | --------- 
| Grootheden |  <a href='/?python#tutorial-values'>make your own list using Tutorial Values </a>  | This list Grootheden that can be used in the webservices |
| Eenheden |  <a href='/?python#tutorial-values'>make your own list using Tutorial Values </a>  | This list Eenheden that can be used in the webservices |
| Compartimenten |  <a href='/?python#tutorial-values'>make your own list using Tutorial Values </a>  | This list Compartimenten that can be used in the webservices |
LocatieLijst | Vul dit later aan | vul dit later aan

