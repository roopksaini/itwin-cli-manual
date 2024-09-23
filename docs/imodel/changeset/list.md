# itp imodel changeset list

List all changesets for a specific iModel.

## Options

- **`--iModelId`**  
  The ID of the iModel whose changesets you want to list.  
  **Type:** `string` **Required:** Yes

- **`--top`**  
  The maximum number of changesets to return.  
  **Type:** `number` **Required:** No

- **`--skip`**  
  The number of changesets to skip.  
  **Type:** `number` **Required:** No

## Examples

```bash
# Example 1: List the first 10 changesets for a specific iModel
itp imodel changeset list --iModelId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --top 10

# Example 2: Skip the first 5 changesets and return the next 10
itp imodel changeset list --iModelId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --skip 5 --top 10

# Example 3: List all changesets without pagination
itp imodel changeset list --iModelId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51"
```

## API Reference

[List Changesets](https://developer.bentley.com/apis/imodels-v2/operations/get-imodel-changesets/)
