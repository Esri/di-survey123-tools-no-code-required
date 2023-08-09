# Survey123 data workflows using ArcGIS for Data Interoperability

## Purpose:

This repo is to show no-code solutions built with Data Interoperability for most common patterns of managing data collected with Survey123 forms. <br/>

Survey123 is a very popular app in the ArcGIS Platform. It's easy to deploy and is used to collect data because of its rich features. However, there are user scenarios where collected data needs to be exported to other systems or even for archiving purposes. Thus, it is quite common for data owners to export their survey data and transform the data  according to their business needs. Often, their surveys have attachments and media collected by the field user. <br/>

A python solution is available [Export Task solution using python](https://github.com/Esri/Survey123-tools/blob/main/Export_survey_data_with_attachments/README.md) in this repo.  


## Use Cases:
1. [Export Survey attachments into Windows folder (fmw)](Use case 1 - Export survey attachment to windows folder(Workbench)
/README.md)<br/>
2. [Export Survey responses and attachment infomation into an Excel report (fmw)](Use case 2 - Export survey responses to Excel report (Workbench)/README.md)
3. Change detection workflow for responses and attachments - coming soon


> [!NOTE]
> New to Data Interoperability, please keep reading below.

### Four ways to build DI solutions

The solutions that will be published in this repo will be built using any of the following DI features. The feature to be used mostly depends on the persona of the tool user. The frequency of use would be another consideration. Other considerations include deployment with Pro, Enterprise or even safe Software's FME Server. 

* Workbench file (fmw) - most data admin or data owners will build a tool using Data Interoperability's Workbench app, a cloned version to FME Desktop. The authored workbench file (FMW) can be stored in the file system and used without launching Pro, as long as the DI extension license is assigned to the user. A workbench file can also be executed through python or command line for automation purposes.

* Spatial ETL Tool (atbx) - this feature is launched from Pro. It starts as a GP tool, and authored from the Workbench app. This feature is best for tools that are frequently run by end users or through Pro's scheduled task.

* Web Tools (GP Service) This feature is a published Spatial ETL tool run from Pro or a browser. Since it's a GP service, its RES end point can be tightly integrated with web apps. This tool is best for end users and inegration with other web solutions. Currently, there are no triggers or scheduling for web tool solutions.

* Quick Tools (GP toolset) This feature is for simple workflow that uses the most common ESRI data formats.  There ae two quick tools, one tool for Export and another one for Import.  This feature is very limited in use and capability.


> [!WARNING] 
> Since the FMW file in git appears as a text file, they will always be made available as zipped fmw or fmwt format.  

## Resources

Below are links to essential references used in the blogs.

* ESRI Based workflows:<br/>
    1. [Event-Driven Integrations with Data Interoperability](https://community.esri.com/t5/arcgis-data-interoperability-blog/event-driven-integrations-with-data/ba-p/883772)<br/>
    2. [Using Data Interoperability to sync data to ArcGIS Online](https://community.esri.com/t5/arcgis-data-interoperability-blog/using-data-interoperability-to-sync-data-to-arcgis/ba-p/903871)<br/>
* Safe's FME Server based Survey123 workflows
    1. [Automating Workflows from Survey123 to ArcGIS using FME Server](https://community.safe.com/s/article/automating-workflows-from-survey123-to-arcgis-usin)<br/>
    
<br/>


## Contributing

Esri welcomes contributions from anyone and everyone. Please see our [guidelines for contributing](https://github.com/esri/contributing).

## Licensing
Copyright © 2023 Esri.

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

(Esri Tags: ArcGIS Data Interoperability for Pro)<br/>
(Esri Tags: Survey123)
