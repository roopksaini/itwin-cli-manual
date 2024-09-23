# itp access-control member user info

Retrieve details about a specific user member in an iTwin.

## Options

- **`--iTwinId`**  
  The ID of the iTwin where the user is a member.  
  **Type:** `string` **Required:** Yes

- **`--memberId`**  
  The ID of the user to retrieve information about.  
  **Type:** `string` **Required:** Yes

## Examples

```bash
itp access-control member user info --iTwinId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --memberId "user1-id"
```

## API Reference

[Get iTwin User Member](https://developer.bentley.com/apis/access-control-v2/operations/get-itwin-user-member/)
