# itp imodel connection sourcefile add

Add a source file to an existing storage connection of an iModel.

## Options

- **`--iModelId`**  
  The ID of the iModel associated with the connection.  
  **Type:** `string` **Required:** Yes

- **`--connectionId`**  
  The ID of the storage connection to which the source file will be added.  
  **Type:** `string` **Required:** Yes

- **`--storageFileId`**  
  The storage file ID.  
  **Type:** `string` **Required:** Yes

- **`--connectorType`**  
  The connector type for synchronization.  
  **Type:** `string` **Required:** Yes  
  **Valid Values:** `"AUTOPLANT"`, `"CIVIL"`, `"CIVIL3D"`, `"DWG"`, `"IFC"`, `"MSTN"`, `"REVIT"`, `"OPENROADS"`, `"SPX"`, `"XER"`, `"PRIMAVERA"`, `"SYNCHRO"`, `"MICROSTATION"`

## Examples

```bash
# Example 1: Add a source file to a storage connection
itp imodel connection sourcefile add --iModelId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --connectionId "bf4d8b36-25d7-4b72-b38b-12c1f0325f42" --storageFileId "t5bDFuN4qUa9ojVw1E5FGtldp8BgSbNCiJ2XMdiT-cA" --connectorType "MSTN"
```

## API Reference

[Add Storage Connection SourceFile](https://developer.bentley.com/apis/synchronization/operations/add-storage-connection-sourcefile/)
