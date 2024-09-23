# itp imodel connection sourcefile list

List all source files in a specific storage connection of an iModel.

## Options

- **`--iModelId`**  
  The ID of the iModel whose connection source files you want to list.  
  **Type:** `string` **Required:** Yes

- **`--connectionId`**  
  The ID of the storage connection.  
  **Type:** `string` **Required:** Yes

## Examples

```bash
itp imodel connection sourcefile list --iModelId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --connectionId "bf4d8b36-25d7-4b72-b38b-12c1f0325f42"
```

## API Reference

[Get Storage Connection SourceFiles](https://developer.bentley.com/apis/synchronization/operations/get-storage-connection-sourcefiles/)
