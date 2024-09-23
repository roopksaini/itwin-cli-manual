# itp imodel connection run create

Run the specified storage connection to synchronize files with an iModel.

## Options

- **`--iModelId`**  
  The ID of the iModel associated with the connection.  
  **Type:** `string` **Required:** Yes

- **`--connectionId`**  
  The ID of the storage connection to run.  
  **Type:** `string` **Required:** Yes

## Examples

```bash
# Example 1: Running a storage connection for an iModel
itp imodel connection run create --iModelId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --connectionId "bf4d8b36-25d7-4b72-b38b-12c1f0325f42"
```

## API Reference

[Run Storage Connection](https://developer.bentley.com/apis/synchronization/operations/run-storage-connection/)
