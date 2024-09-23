# itp imodel connection create

Create a storage connection that describes files from storage to synchronize with an iModel.

## Options

- **`--iModelId`**  
  The ID of the iModel.  
  **Type:** `string` **Required:** Yes

- **`--sourceFiles`**  
  A list of source files to synchronize.  
  **Type:** `array` **Required:** Yes

- **`--displayName`**  
  The display name of the storage connection.  
  **Type:** `string` **Required:** No

- **`--authenticationType`**  
  The authorization workflow type.  
  **Type:** `string` **Required:** No  
  **Valid Values:** `"User"`, `"Service"`

## Examples

```bash
# Example 1: Minimal example with only required options
itp imodel connection create --iModelId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --sourceFiles "file1.dwg file2.dgn"

# Example 2: Creating a connection with Service authentication
itp imodel connection create --iModelId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --displayName "Engineering Files" --authenticationType "Service" --sourceFiles "blueprints.pdf model.ifc"
```

## API Reference

[Create Storage Connection](https://developer.bentley.com/apis/synchronization/operations/create-storage-connection/)
