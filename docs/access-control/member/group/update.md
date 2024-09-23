# itp access-control member group update

Update the role assignments for a group in an iTwin.

## Options

- **`--iTwinId`**  
  The ID of the iTwin where the group is a member.  
  **Type:** `string` **Required:** Yes

- **`--groupId`**  
  The ID of the group whose roles will be updated.  
  **Type:** `string` **Required:** Yes

- **`--roleIds`**  
  A list of role IDs to assign to the group.  
  **Type:** `array` **Required:** Yes

## Examples

```bash
itp access-control member group update --iTwinId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --groupId "group1-id" --roleIds '["role1-id", "role2-id"]'
```

## API Reference

[Update iTwin Group Member](https://developer.bentley.com/apis/access-control-v2/operations/update-itwin-group-member/)
