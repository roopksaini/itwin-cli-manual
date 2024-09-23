# itp imodel connection update

Update an existing storage connection for an iModel.

## Options

- **`--iModelId`**  
  The ID of the iModel.  
  **Type:** `string` **Required:** Yes

- **`--connectionId`**  
  The ID of the storage connection to update.  
  **Type:** `string` **Required:** Yes

- **`--displayName`**  
  The new display name for the storage connection.  
  **Type:** `string` **Required:** No

- **`--authenticationType`**  
  The authorization workflow type.  
  **Type:** `string` **Required:** No  
  **Valid Values:** `"User"`, `"Service"`

## Examples

```bash
# Example 1: Updating a connection with a new display name
itp imodel connection update --iModelId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --connectionId "bf4d8b36-25d7-4b72-b38b-12c1f0325f42" --displayName "Updated Project Files"

# Example 2: Changing authentication type for a connection
itp imodel connection update --iModelId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --connectionId "bf4d8b36-25d7-4b72-b38b-12c1f0325f42" --authenticationType "Service"
```

## API Reference

[Update Storage Connection](https://developer.bentley.com/apis/synchronization/operations/update-storage-connection/)
