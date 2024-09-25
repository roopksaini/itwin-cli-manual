# itp imodel connection sourcefile update

Update an existing source file in a storage connection of an iModel.

## Options

- **`--connectionId`**  
  The ID of the storage connection.  
  **Type:** `string` **Required:** Yes

- **`--sourceFileId`**  
  The source file ID to update.  
  **Type:** `string` **Required:** Yes

- **`--connectorType`**  
  The connector type for synchronization.  
  **Type:** `string` **Required:** Yes  
  **Valid Values:** `"AUTOPLANT"`, `"CIVIL"`, `"CIVIL3D"`, `"DWG"`, `"IFC"`, `"MSTN"`, `"REVIT"`

## Examples

```bash
itp imodel connection sourcefile update --connectionId "bf4d8b36-25d7-4b72-b38b-12c1f0325f42" --sourceFileId "297c8ab9-53a3-4fe5-adf8-79b4c1a95cbb" --connectorType "DWG"
```

## API Reference

[Update Storage Connection SourceFile](https://developer.bentley.com/apis/synchronization/operations/update-storage-connection-sourcefile/)
