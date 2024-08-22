# itwin-cli itwin update

Update the specified iTwin. Only include properties you want to update.

## Options

- **`--id`**  
  The ID of the iTwin to be updated.  
  **Type:** `string` **Required:** Yes

- **`--class`**  
  The Class of your iTwin.  
  **Type:** `string` **Required:** No

- **`--subClass`**  
  The subClass of your iTwin.  
  **Type:** `string` **Required:** No

- **`--type`**  
  Defines the iTwin's Type.  
  **Type:** `string` **Required:** No

- **`--displayName`**  
  The iTwin's display name.  
  **Type:** `string` **Required:** No

- **`--number`**  
  Unique identifier for the iTwin.  
  **Type:** `string` **Required:** No

- **`--geographicLocation`**  
  Optional location, typically an address or city.  
  **Type:** `string, null` **Required:** No

- **`--ianaTimeZone`**  
  Optional IANA time zone ID.  
  **Type:** `string, null` **Required:** No

- **`--status`**  
  Status of the iTwin. Defaults to Active.  
  **Type:** `iTwinStatus` **Required:** No  
  **Valid Values:** `"Active"`, `"Inactive"`, `"Trial"`

## Examples

```bash
itwin-cli itwin update --id "12345abcde" --class "Utilities" --subClass "Power Plant" --displayName "Updated Solar Farm"
itwin-cli itwin update --id "12345abcde" --displayName "New Display Name" --geographicLocation "New City, CA" --ianaTimeZone "America/Chicago"
itwin-cli itwin update --id "12345abcde" --status "Inactive"
itwin-cli itwin update --id "12345abcde" --number "LAPTX-002" --type "Standard"
itwin-cli itwin update --id "12345abcde" --geographicLocation "Updated Address" --ianaTimeZone "Europe/London" --status "Trial"
```

## API Reference

https://developer.bentley.com/apis/itwins/operations/update-itwin/