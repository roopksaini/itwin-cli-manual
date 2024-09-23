# itp access-control role update

Update the details of an existing role in an iTwin.

## Options

- **`--iTwinId`**  
  The ID of the iTwin where the role exists.  
  **Type:** `string` **Required:** Yes

- **`--roleId`**  
  The ID of the role to be updated.  
  **Type:** `string` **Required:** Yes

- **`--displayName`**  
  The updated name of the role.  
  **Type:** `string` **Required:** No

- **`--description`**  
  The updated description of the role.  
  **Type:** `string` **Required:** No

- **`--permissions`**  
  A list of permissions to assign to the role.  
  **Type:** `array` **Required:** No

## Examples

```bash
# Example 1: Update role name and description
itp access-control role update --iTwinId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --roleId "role1-id" --displayName "Lead Engineer" --description "Oversees engineering tasks"

# Example 2: Update role permissions along with the name
itp access-control role update --iTwinId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --roleId "role1-id" --displayName "Admin Role" --permissions '["Permission1", "Permission2", "Permission3"]'
```

## API Reference

[Update iTwin Role](https://developer.bentley.com/apis/access-control-v2/operations/update-itwin-role/)
