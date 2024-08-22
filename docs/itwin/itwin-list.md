# itwin-cli itwin list

List all iTwins associated with the calling user.

## Options

- **`--subClass`**  
  Filter by a specific iTwin subClass.  
  **Type:** `string` **Required:** No

- **`--status`**  
  Filter by the status of the iTwin.  
  **Type:** `string` **Required:** No  
  **Valid Values:** `"Active"`, `"Inactive"`, `"Trial"`

- **`--type`**  
  Filter by the iTwin's Type.  
  **Type:** `string` **Required:** No

- **`--number`**  
  Find iTwins with the exact number specified.  
  **Type:** `string` **Required:** No

- **`--displayName`**  
  Find iTwins with the exact display name specified.  
  **Type:** `string` **Required:** No

- **`--parentId`**  
  Filter by the parent iTwin ID.  
  **Type:** `string` **Required:** No

- **`--iTwinAccountId`**  
  Filter by the iTwin Account ID.  
  **Type:** `string` **Required:** No

- **`--search`**  
  Search iTwins by a string in the number or display name.  
  **Type:** `string` **Required:** No

- **`--top`**  
  Limit the number of items returned.  
  **Type:** `integer` **Required:** No

- **`--skip`**  
  Skip a number of items in the result.  
  **Type:** `integer` **Required:** No

- **`--includeInactive`**  
  Include Inactive iTwins in the result.  
  **Type:** `boolean` **Required:** No

## Examples

```bash
itwin-cli itwin list --subClass "Bridge" --status "Active"
itwin-cli itwin list --type "Luxury" --top 10
itwin-cli itwin list --displayName "Solar Farm" --includeInactive true
itwin-cli itwin list --parentId "12345abcde" --skip 5
itwin-cli itwin list --search "Downtown" --top 5
```

## API Reference

https://developer.bentley.com/apis/itwins/operations/get-my-itwins/