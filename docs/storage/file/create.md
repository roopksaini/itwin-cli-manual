# itp storage file create

Create a new file in an iTwin's storage.

## Options

- **`--iTwinId`**  
  The ID of the iTwin where the file will be created.  
  **Type:** `string` **Required:** Yes

- **`--fileName`**  
  The name of the file to be created.  
  **Type:** `string` **Required:** Yes

## Examples

```bash
# Example 1: Create a file in iTwin's storage
itp storage file create --iTwinId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --fileName "design.dwg"

# Example 2: Create another file in the same iTwin
itp storage file create --iTwinId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --fileName "model.ifc"
```

## API Reference

[Create File](https://developer.bentley.com/apis/storage/operations/create-file/)
