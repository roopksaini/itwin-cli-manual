# itp storage folder update

Update the metadata of a folder in an iTwin's storage, such as its display name or description.

## Options

- **`--folderId`**  
  The ID of the folder to be updated.  
  **Type:** `string` **Required:** Yes

- **`--folderName`**  
  The new name for the folder.  
  **Type:** `string` **Required:** No

- **`--description`**  
  A description for the folder.  
  **Type:** `string` **Required:** No

## Examples

```bash
# Example 1: Update folder name
itp storage folder update --folderId "a1b2c3d4-5678-90ab-cdef-1234567890ab" --folderName "Updated Project Documents"

# Example 2: Update folder name and description
itp storage folder update --folderId "b2c3d4e5-6789-01ab-cdef-2345678901bc" --folderName "Updated Design Files" --description "Folder containing updated design documents"
```

## API Reference

[Update Folder](https://developer.bentley.com/apis/storage/operations/update-folder/)
