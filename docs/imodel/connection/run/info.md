# itp imodel connection run info

Retrieve details about a specific run of a storage connection of an iModel.

## Options

- **`--iModelId`**  
  The ID of the iModel associated with the connection run.  
  **Type:** `string` **Required:** Yes

- **`--connectionRunId`**  
  The ID of the storage connection run.  
  **Type:** `string` **Required:** Yes

## Examples

```bash
itp imodel connection run info --iModelId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --connectionRunId "abc12345-6789-4321-abcd-9876543210ef"
```

## API Reference

[Get Storage Connection Run](https://developer.bentley.com/apis/synchronization/operations/get-storage-connection-run/)
