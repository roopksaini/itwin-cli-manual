# itp access-control role info

Retrieve details about a specific role in an iTwin.

## Options

- **`--iTwinId`**  
  The ID of the iTwin where the role exists.  
  **Type:** `string` **Required:** Yes

- **`--roleId`**  
  The ID of the role to retrieve information about.  
  **Type:** `string` **Required:** Yes

## Examples

```bash
itp access-control role info --iTwinId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --roleId "role1-id"
```

## API Reference

[Get iTwin Role Info](https://developer.bentley.com/apis/access-control-v2/operations/get-itwin-role/)
