# itp imodel connection run info

Retrieve details about a specific run of a storage connection.

## Options

- **`--connectionId`**  
  The ID of the storage connection associated with the run.  
  **Type:** `string` **Required:** Yes

- **`--connectionRunId`**  
  The ID of the storage connection run.  
  **Type:** `string` **Required:** Yes

## Examples

```bash
itp imodel connection run info --connectionId "abc12345-6789-4321-abcd-9876543210ef" --connectionRunId "run98765-4321-abcd-1234-567890abcdef"
```

## API Reference

[Get Storage Connection Run](https://developer.bentley.com/apis/synchronization/operations/get-storage-connection-run/)
