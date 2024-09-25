# itp itwin update

Update the specified iTwin. Only include properties you want to update.

## Options

- **`--id`**  
  The ID of the iTwin to be updated.  
  **Type:** `string` **Required:** Yes

- **`--class`**  
  The Class of your iTwin.  
  **Type:** `string` **Required:** No  
  **Valid Values:** `"Account"`, `"Thing"`, `"Endeavor"`

- **`--subClass`**  
  The subClass of your iTwin.  
  **Type:** `string` **Required:** No  
  **Valid Values:** `"Account"`, `"Portfolio"`, `"Asset"`, `"Program"`, `"Project"`, `"WorkPackage"`

- **`--type`**  
  Open ended property to define your iTwin's type.
  **Type:** `string` **Required:** No

- **`--displayName`**  
  The iTwin's display name.  
  **Type:** `string` **Required:** No

- **`--number`**  
  Unique identifier for the iTwin.  
  **Type:** `string` **Required:** No

- **`--geographicLocation`**  
  Optional location, typically an address or city.  
  **Type:** `string` **Required:** No

- **`--ianaTimeZone`**  
  Optional IANA time zone ID.  
  **Type:** `string` **Required:** No

- **`--status`**  
  Status of the iTwin. Defaults to Active.  
  **Type:** `iTwinStatus` **Required:** No  
  **Valid Values:** `"Active"`, `"Inactive"`, `"Trial"`

## Examples

```bash
# Example 1: Updating iTwin's class and display name
itp itwin update --id "b1a2c3d4-5678-90ab-cdef-1234567890ab" --class "Endeavor" --subClass "Project" --displayName "Updated Solar Farm"

# Example 2: Changing geographic location and time zone
itp itwin update --id "b1a2c3d4-5678-90ab-cdef-1234567890ab" --geographicLocation "New City, CA" --ianaTimeZone "America/Chicago"

# Example 3: Setting the status to inactive
itp itwin update --id "b1a2c3d4-5678-90ab-cdef-1234567890ab" --status "Inactive"
```

## API Reference

[Update iTwin](https://developer.bentley.com/apis/itwins/operations/update-itwin/)
