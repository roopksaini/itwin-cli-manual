# itp imodel named-version info

Retrieve details about a specific named version in an iModel.

## Options

- **`--iModelId`**  
  The ID of the iModel whose named version you want to retrieve.  
  **Type:** `string` **Required:** Yes

- **`--namedVersionId`**  
  The ID of the named version.  
  **Type:** `string` **Required:** Yes

## Examples

```bash
itp imodel named-version info --iModelId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51" --namedVersionId "bf4d8b36-25d7-4b72-b38b-12c1f0325f42"
```

## API Reference

[Get Named Version Details](https://developer.bentley.com/apis/imodels-v2/operations/get-imodel-named-version-details/)
