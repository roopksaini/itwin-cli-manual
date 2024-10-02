# itp imodel connection auth

Generate a refresh token to maintain connection validity for long-running tasks.

## Options

- **`--redirectUrl`**
  (Optional) URL to redirect back to after authorization.  
  **Type:** `string` **Required:** No

## Examples

```bash
# Example 1: Authenticate user and get authorization information for an iModel connection
itp imodel connection auth

# Example 2: Authenticate with a specific redirect URL after authorization
itp imodel connection auth --redirectUrl "https://example.com/callback"
```

## API Reference

[Get Authorization Information](https://dev-developer.bentley.com/apis/synchronization/operations/get-authorization-information/)
