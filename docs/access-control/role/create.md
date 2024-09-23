# itp access-control role create

Create a new role for an iTwin. To assign permissions after creation, use `itp access-control role update`.

## Options

- **`--iTwinId`**  
  The ID of the iTwin for which the role is being created.  
  **Type:** `string` **Required:** Yes

- **`--displayName`**  
  The name of the role to be created.  
  **Type:** `string` **Required:** Yes

- **`--description`**  
  A description of the role.  
  **Type:** `string` **Required:** No

## Examples

```bash
itp access-control role create --iTwinId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --displayName "Project Manager" --description "Manages all aspects of the project"
```

## API Reference

[Create iTwin Role](https://developer.bentley.com/apis/access-control-v2/operations/create-iTwin-role/)
