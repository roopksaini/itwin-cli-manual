# itp imodel connection sourcefile info

Retrieve details about a specific source file in a storage connection of an iModel.

## Options

- **`--connectionId`**  
  The ID of the storage connection.  
  **Type:** `string` **Required:** Yes

- **`--sourceFileId`**  
  The ID of the source file to retrieve.  
  **Type:** `string` **Required:** Yes

## Examples

```bash
itp imodel connection sourcefile info --connectionId "bf4d8b36-25d7-4b72-b38b-12c1f0325f42" --sourceFileId "297c8ab9-53a3-4fe5-adf8-79b4c1a95cbb"
```

## API Reference

[Get Storage Connection SourceFile](https://developer.bentley.com/apis/synchronization/operations/get-storage-connection-sourcefile/)
