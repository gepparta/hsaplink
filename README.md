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
  * **GETOBJECTTYPE** - return SAP Object Type which this Plugin is handling (ex. CLAS, TTYP ..)
  * **CHECKEXISTS** - check if the object to be imported already exist
  * **CREATEIXMLDOCFROMOBJECT** - prepare XML document with attributes and Childs in **IXMLDOCUMENT** parameter
  * **CREATEOBJECTFROMIXMLDOC** - fetch XML from import parameter **IXMLDOCUMENT** and create into SAP DB
  * **DELETEOBJECT** - delete object if Overwrite is selected

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
