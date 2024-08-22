# itwin-cli imodel changesets

Retrieve a list of changesets for the specified iModel by its ID.

## Options

- **`--id`**  
  The ID of the iModel.  
  **Type:** `string` **Required:** Yes

- **`--top`**  
  Limit the number of changesets returned.  
  **Type:** `integer` **Required:** No

- **`--skip`**  
  Skip a number of changesets in the result.  
  **Type:** `integer` **Required:** No

- **`--orderBy`**  
  Order the changesets by a specific property.  
  **Type:** `string` **Required:** No  
  **Valid Values:** `"index asc"`, `"index desc"`

- **`--afterIndex`**  
  Retrieve changesets with an index greater than the specified value.  
  **Type:** `integer` **Required:** No

- **`--lastIndex`**  
  Retrieve changesets with an index less than or equal to the specified value.  
  **Type:** `integer` **Required:** No

## Examples

```bash
itwin-cli imodel changesets --id "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --top 5
itwin-cli imodel changesets --id "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --skip 10 --orderBy "index desc"
itwin-cli imodel changesets --id "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --afterIndex 10 --lastIndex 20
```

## API Reference

https://developer.bentley.com/apis/imodels-v2/operations/get-imodel-changesets/