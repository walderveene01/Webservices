---
title: Webservices

language_tabs: 

  - python: Python
  - json: JSON Request
  - shell: JSON Response

toc_footers:
  - <a href='www.waterinfo.rws.nl'>Website Waterinfo</a>


includes:
  - TutorialLoc
  - TutorialPara
  - MetaDataservice
  - OnlineWaarnemingenservice
  - BulkWaarnemingService
  - WebFeatureServices
  - version
  - errors


search: true
---
# Introduction
```python
// Nothing to show
```

```json
// Nothing to show
```

```shell
// Nothing to show
```
<aside class="notice">
Check the following languages  on the right  ------ >
</aside>
The system is intended to access/retrieve the data in the distributie laag through web services. the
data is accessed through five web services (three HTTP JSON web services and two WFS
web service):
  
Webservices |
| ----- |
| MetadataService |
| Online Waarnemingen Service |
| Bulk Waarnemingen Service |
| Web Feature Service |
| Web Mapping Service | 


**Metadata Service** 

The Metadata Service consists of one function:

Function |
| ----- |
| Ophalen Catalogus |

A request for these service tasks is provided several lists on metadata from the
distributie laag. On the basis of the data in these lists, one can fill in forms for one of the four
OnlineWaarnemingenServices.

**OnlineWaarnemingenServices**

The OnlineWaarnemingenServices consists of four functions:

 Function | 
| ----- |
| Ophalen Waarnemingen | 
| Ophalen Laatste Waarnemingen | 
| Ophalen Aantal Waarnemingen | 
| Check Waarnemingen Aanwezig

With a request to the OphalenWaarnemingen service it is possible observations to die
meet the specified parameters. These parameters relate to the Aquometadata, Locatie
and Periode the observations have been performed. An application to the OphalenLaatsteWaarnemingenService retrieves the last observation that has been given from the Aquametadata concerned
attributes. The service Ophalen laatste Waarnemingen is the number of observations per grouped
specified grouping period. The CheckWaarnemingenAanwezigService returns from there observations
the distributie laag are those that comply with the parameters provided.


**BulkWaarnemingenService**

The BulkWaarnemingenService consists of one function:

Function |
| ----- | 
| Aanvragen Bulk Waarnemingen

With the AanvragenBulkWaarnemingen service an application can be made to a
a server that can be downloaded from a Rijkswaterstaat server at a later time.

**Web Feature Service**

The Web Feature Service consists of two functions:
  
Function |
| ----- |
| Locaties
| Locaties Met Laatste Waarneming

With the Mapserver, the geometry within the distributie laag is made available through Web
Feature Service. Through the Web Feature Service one can find the locaties and locaties in combination with the last 
Observation .

**Web Mapping Service**

The Web Mapping Service consists of a service with a Get Functions:
  
Function | 
| ------ | 
| WMS versie 1.1.0
| WMS versie 1.1.1
| WMS versie 1.3.0

The Mapping service responds to an xml with a description of the layers.
The Getmap service provides an image of the specified area.
The Getfeature provides the details of a feature per location as an answer.

**Dependence**

The web services depend on the distributie laag. When the distributie laag is not functioning properly,
this has an influence on the functioning of the web services. Create all web services and the Web Feature Service
use of the Locatie, aquometadata and observations in the distributie laag.
