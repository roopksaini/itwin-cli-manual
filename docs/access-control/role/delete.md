# itp access-control role delete

Delete an existing role from an iTwin.

## Options

- **`--iTwinId`**  
  The ID of the iTwin where the role exists.  
  **Type:** `string` **Required:** Yes

- **`--roleId`**  
  The ID of the role to be deleted.  
  **Type:** `string` **Required:** Yes

## Examples

```bash
itp access-control role delete --iTwinId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --roleId "role1-id"
```

## API Reference

[Delete iTwin Role](https://developer.bentley.com/apis/access-control-v2/operations/delete-itwin-role/)
