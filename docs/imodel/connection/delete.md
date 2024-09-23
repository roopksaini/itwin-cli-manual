# itp imodel connection delete

Delete a storage connection from an iModel.

## Options

- **`--iModelId`**  
  The ID of the iModel.  
  **Type:** `string` **Required:** Yes

- **`--connectionId`**  
  The ID of the storage connection to delete.  
  **Type:** `string` **Required:** Yes

## Examples

```bash
itp imodel connection delete --iModelId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --connectionId "bf4d8b36-25d7-4b72-b38b-12c1f0325f42"
```

## API Reference

[Delete Storage Connection](https://developer.bentley.com/apis/synchronization/operations/delete-storage-connection/)
