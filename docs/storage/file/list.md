# itp storage file list

List files in a folder of an iTwin's storage. Optionally, include subfolders in the result.

## Options

- **`--folderId`**  
  The ID of the folder whose files you want to list.  
  **Type:** `string` **Required:** Yes

- **`--includeFolders`**  
  Whether to include subfolders in the result.  
  **Type:** `boolean` **Required:** No

## Examples

```bash
# Example 1: List files in a specific folder
itp storage file list --folderId "b1a2c3d4-5678-90ab-cdef-1234567890ab"

# Example 2: List files and include subfolders in the result
itp storage file list --folderId "b1a2c3d4-5678-90ab-cdef-1234567890ab" --includeFolders true
```

## API Reference

[List Files in Folder](https://developer.bentley.com/apis/storage/operations/get-files-in-folder/)  
[List Files and Folders](https://developer.bentley.com/apis/storage/operations/get-folders-and-files-in-folder/)
