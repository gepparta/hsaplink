# SAPLink Project

* [SAPLink](https://www.assembla.com/spaces/saplink-plugins/wiki) is a tool to Import/Export SAP Objects as Nuggets (.nugg) files.
* This supports [Plugins](https://www.assembla.com/spaces/saplink/wiki/SAPlink_plugin_list) which will enable SAP Objects (like Tables, Classes) to be supported by SAPLink

## Nuggets
  Used Import/Export ABAP Objects into files.

## SAPLinkee
  Used to store single ABAP Object into a file, usually for SAPLink plugins

## SAPLink Plugin
* Should inherit from Super class **ZSAPLINK**
* Implement following minimum methods for a Plugin

|Method|Usage|
|---|---|
|**GETOBJECTTYPE** | return SAP Object Type which this Plugin is handling (ex. CLAS, TTYP ..) |
|**CHECKEXISTS** | check if the object to be imported already exist|
| **CREATEIXMLDOCFROMOBJECT** | prepare XML document with attributes and Childs in **IXMLDOCUMENT** parameter |
| **CREATEOBJECTFROMIXMLDOC** | fetch XML from import parameter **IXMLDOCUMENT** and create into SAP DB |
| **DELETEOBJECT** | delete object if Overwrite is selected |

# Custom Plugins Developed (dev/plugins)
  |SLinkee|Usage|
  |---|---|
  | **CLAS_ZSAPLINK_NUMBER_RANGES** | Number Ranges|
  | **CLAS_ZSAPLINK_DESIGN_LAYER_CONFIG** | CRM Ui Design Layer Configuration|

# Installing SAPLink
  * for latest **SAPLINK** installer zip, check [SAPLink Wiki](https://www.assembla.com/spaces/saplink-plugins/wiki)
  * Download **SAPlink_Daily.nugg.zip** from trunk/build
  * Copy code inside **ZSAPLINK_INSTALLER.TXT** file to a ABAP Report
  * Execute the report and provide **SAPlink_Daily.nugg** as input (Note: import it twice to avoid importing issues)
  * Activate all ***Worklist*** objects in **$TMP**
  * Use **SAPLINK** report to import/export Nuggets and SLinkees.

## Header Info
```
*/---------------------------------------------------------------------\
*|   This file is part of SAPlink.                                     |
*|                                                                     |
*|   The code of this project is provided to you under the current     |
*|   version of the SAP Code Exchange Terms of Use. You can find the   |
*|   text on the SAP Code Exchange webpage at http://www.sdn.sap.com   |
*|                                                                     |
*|   SAPlink is provided to you AS IS with no guarantee, warranty or   |
*|   support.                                                          |
*\---------------------------------------------------------------------/
*      Plugin created by:
*      Hareesh Polla
*      hareeshbabu82@gmail.com
```
