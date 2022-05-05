# Exporting Survey123 survey data with Data Interoperability

Survey123 is a very popular app in the ESRI stack. Its easy to deploy and use to collect data because of its rich features. However, there are times that the data will have to be exported to other systems or even for archiving purposes. Thus, it is quite common for data owners to export their survey data and shape or transform  the data  according to their business needs. Often, their surveys have different attachments and media that have been collected by the field user.   <br/>

## Solution details
The ETL tool created for this workflow is authored in its simplest form. It reads all the features of a Survey123 feature layer using the [AGOL Feature Service layer reader](https://docs.safe.com/fme/html/FME_Desktop_Documentation/FME_ReadersWriters/arcgisonlinefeatures/arcgisonlinefeatures.htm). It exposes the feature attachments as a list and explodes this list into attachment features linked to the original survey's globalID using the [ListExploder](http://docs.safe.com/fme/html/FME_Desktop_Documentation/FME_Transformers/Transformers/listexploder.htm) transformer. <br/>

The attribute able of the attachment features look similar to the screenshot below. </br>




The image attachment is stored as a blob on the survey data attachment table. Once exploded, the attribute column data (in blob type) is written as a JPEG file by the [AtributeFileWriter](http://docs.safe.com/fme/html/FME_Desktop_Documentation/FME_Transformers/Transformers/attributefilewriter.htm) transformer, using the name attribute value as the jpeg filename <br/>

Below is a screenshot of the solution. <br/>

![image](https://user-images.githubusercontent.com/87094963/166831682-d5e9968d-14c1-4d3a-b2e6-b020d0150970.png)

The [Inspector](http://docs.safe.com/fme/html/FME_Desktop_Documentation/FME_Transformers/Transformers/inspeector.htm) transformer is a placeholder for any other output formats that the user may want to add to the workspace, whether its an Excel writer, a geodatabase, Enterprise or AGOL faeture layers, JSON or any of [400 plus supported formats of Data Interoperabilty](https://pro.arcgis.com/en/pro-app/latest/help/data/data-interoperability/supported-formats-with-the-data-interoperability-extension.htm).<br/>


## Instructions

    Prerequisites:
    - A Survey123 survey and collected data with image attachments and annotations. For this blog the Survey123 Connect sample Images and Annotation survey was used. This sample survey is shared [publicly](https://survey123.arcgis.com/share/1a4a4e91484d4175b340b7f8b9a1dfa3?portalUrl=https://PM.maps.arcgis.com). You are welcome to add to the survey.
    - An AGOL Organizational account.
    - Configure a Web Connection of your AGOL account in the Tools Options of Data Interoperability. 
    - Identify the destination folder for your attachments

1. Download and open the workspace file from this repo.
2. New DI users: Delete the connection between the AGOL reader and the ListExploder transformer. Advanced DI users: go to the Readers menu and select Import 








## Requirements

* ArcGIS Pro 2.9 or higher
* Data Interoperability for ArcGIS Pro 2.9 or e


## Resources

Below are links to essential references used in the blogs.

* [Utility Network Upgrade History (Doc)](https://pro.arcgis.com/en/pro-app/latest/help/data/utility-network/utility-network-upgrade-history.htm)<br/>
* JSON tutorial references:<br/>
    1. [Ontario511](https://pm.maps.arcgis.com/home/item.html?id=4ec1d2420089451bb173e90ce01e2e0a)<br/>
    2. [Import Building GeoJSON](https://pm.maps.arcgis.com/home/item.html?id=9da0f8ae5fee45aca11bf77f712884c8)<br/>
    3. [Learn JSON](https://www.youtube.com/watch?v=iiADhChRriM)<br/>

* [Spatial ETL Tool (Doc)](https://pro.arcgis.com/en/pro-app/latest/help/data/data-interoperability/spatial-etl-tools.htm)
* [Automate yor ETL Processes blog](https://community.esri.com/t5/arcgis-data-interoperability-blog/automate-your-etl-processes-on-a-schedule-two-ways/ba-p/883616)<br/>


## Issues

Find a bug or want to request a new feature?  Please let us know by submitting an issue.

## Contributing

Esri welcomes contributions from anyone and everyone. Please see our [guidelines for contributing](https://github.com/esri/contributing).

## Licensing
Copyright 2021 Esri

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

A copy of the license is available in the repository's [license.txt](https://github.com/salvaleonrp/di-data-driven-electric-utility-export-subnetwork/blob/main/license.txt) file.

[](Esri Tags: Data Interoperability for ArcGIS Pro)
[](Esri Tags: Utility Network)
