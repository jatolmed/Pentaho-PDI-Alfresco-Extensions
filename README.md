# Pentaho-PDI-Alfresco-Extensions
Pentaho PDI Alfresco Extensions

Pentaho-PDI-Alfresco-Extensions introduces Alfresco/CMIS file upload feature in PDI.

The extension permits to: 
* upload documents to Alfresco, specifying  DocumentType, Metadata, Destination Folder and to get output in a human-readable format. 


## UPLOADER

### Input
* URL Alfresco
* Username Alfresco
* Password Alfresco
* Path of the file
* Path of Alfresco directory
* DocumentType in Alfresco
* JSON metadata

#### JSON Metadata

| __Data type Alfresco__ | __Mapping Conventions__ |
|-------------|------------|
| d:text | S# ... | 
| d:int | I# ... | 
| d:long | L# ... |
| d:double | D# ... |
| d:boolean | B#true (or) B#false |
| d:date | DT# + date with "dd/MM/yyyy" format |
| d:datetime | TS# + timestamp with "dd/MM/yyyy HH:mm:ss" format |

Example:

```json
{
"myInv:description":"S#80 2018 Favourite Customer",
"myInv:amount":"D#1233.45",
"myInv:date":"TS#01/02/2018 10:35:00"
}
```

### Output
* Upload Status (ok/ko)
* Alfresco Noderef (ObjectID)
* ErrorLog (if any)

### Errors

Errors are in output and the transformations never get aborted by an error.


