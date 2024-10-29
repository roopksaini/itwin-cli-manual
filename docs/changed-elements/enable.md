# itp changed-elements enable

Enable change tracking for a specified iModel.

## Options

- **`--iTwinId`**  
  The ID of the iTwin associated with the iModel.  
  **Type:** `string` **Required:** Yes

- **`--iModelId`**  
  The ID of the iModel where change tracking should be enabled.  
  **Type:** `string` **Required:** Yes

## Examples

```bash
itp changed-elements enable --iTwinId "1a2b3c4d-5678-90ab-cdef-1234567890ab" --iModelId "ad0ba809-9241-48ad-9eb0-c8038c1a1d51"
```

## API Reference

[Enable Change Tracking](https://developer.bentley.com/apis/changed-elements/operations/enable-change-tracking/)
