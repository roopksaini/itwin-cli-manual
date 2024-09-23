# itp access-control member user delete

Remove a user from an iTwin.

## Options

- **`--iTwinId`**  
  The ID of the iTwin where the user is a member.  
  **Type:** `string` **Required:** Yes

- **`--memberId`**  
  The ID of the user to remove from the iTwin.  
  **Type:** `string` **Required:** Yes

## Examples

```bash
itp access-control member user delete --iTwinId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --memberId "user1-id"
```

## API Reference

[Remove iTwin User Member](https://developer.bentley.com/apis/access-control-v2/operations/remove-itwin-user-member/)
