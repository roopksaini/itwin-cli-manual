# itp itwin list

List all iTwins the calling user is a member of.

## Options

- **`--subClass`**  
  Specify the subClass of iTwins to list.  
  **Type:** `string` **Required:** Yes  
  **Valid Values:** `"Account"`, `"Portfolio"`, `"Asset"`, `"Program"`, `"Project"`, `"WorkPackage"`

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
  Include inactive iTwins in the result.  
  **Type:** `boolean` **Required:** No

## Examples

```bash
# Example 1: Filtering by subClass and status
itp itwin list --subClass "Project" --status "Active"

# Example 2: Limiting the number of returned results and filtering by type
itp itwin list --subClass "Program" --type "Luxury" --top 10

# Example 3: Searching by display name and including inactive iTwins
itp itwin list --subClass "Asset" --displayName "Solar Farm" --includeInactive true

# Example 4: Filtering by parent iTwin ID and skipping the first 5 results
itp itwin list --subClass "WorkPackage" --parentId "b1a2c3d4-5678-90ab-cdef-1234567890ab" --skip 5
```

## API Reference

[List iTwins](https://developer.bentley.com/apis/itwins/operations/get-my-itwins/)
