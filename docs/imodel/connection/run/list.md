# itp imodel connection run list

List all runs for a specific storage connection of an iModel.

## Options

- **`--iModelId`**  
  The ID of the iModel whose connection runs you want to list.  
  **Type:** `string` **Required:** Yes

- **`--connectionId`**  
  The ID of the storage connection.  
  **Type:** `string` **Required:** Yes

## Examples

```bash
# Example 1: List all runs for a specific connection
itp imodel connection run list --iModelId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --connectionId "bf4d8b36-25d7-4b72-b38b-12c1f0325f42"
```

## API Reference

[Get Storage Connection Runs](https://developer.bentley.com/apis/synchronization/operations/get-storage-connection-runs/)
