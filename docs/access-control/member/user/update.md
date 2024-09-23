# itp access-control member user update

Update the role assignments for a user in an iTwin.

## Options

- **`--iTwinId`**  
  The ID of the iTwin where the user is a member.  
  **Type:** `string` **Required:** Yes

- **`--memberId`**  
  The ID of the user whose roles will be updated.  
  **Type:** `string` **Required:** Yes

- **`--roleIds`**  
  A list of role IDs to assign to the user.  
  **Type:** `array` **Required:** Yes

## Examples

```bash
itp access-control member user update --iTwinId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --memberId "user1-id" --roleIds '["role1-id", "role2-id"]'
```

## API Reference

[Update iTwin User Member](https://developer.bentley.com/apis/access-control-v2/operations/update-itwin-user-member/)
