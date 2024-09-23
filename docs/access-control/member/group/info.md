# itp access-control member group info

Retrieve details about a specific group member in an iTwin.

## Options

- **`--iTwinId`**  
  The ID of the iTwin where the group is a member.  
  **Type:** `string` **Required:** Yes

- **`--groupId`**  
  The ID of the group to retrieve information about.  
  **Type:** `string` **Required:** Yes

## Examples

```bash
itp access-control member group info --iTwinId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --groupId "group1-id"
```

## API Reference

[Get iTwin Group Member](https://developer.bentley.com/apis/access-control-v2/operations/get-itwin-group-member/)
