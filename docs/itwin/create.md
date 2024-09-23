# itp itwin create

Create a new iTwin with specified properties.

## Options

- **`--class`**  
  The Class of your iTwin.  
  **Type:** `string` **Required:** Yes

- **`--subClass`**  
  The subClass of your iTwin.  
  **Type:** `string` **Required:** Yes

- **`--type`**  
  Defines the iTwin's Type.  
  **Type:** `string` **Required:** No

- **`--displayName`**  
  The iTwin's display name.  
  **Type:** `string` **Required:** Yes

- **`--number`**  
  Unique identifier for the iTwin. Defaults to iTwin Id if unspecified.  
  **Type:** `string` **Required:** No

- **`--geographicLocation`**  
  Optional location, typically an address or city.  
  **Type:** `string, null` **Required:** No

- **`--ianaTimeZone`**  
  Optional IANA time zone ID.  
  **Type:** `string, null` **Required:** No

- **`--dataCenterLocation`**  
  Data center for iTwin data. Defaults to East US.  
  **Type:** `string` **Required:** No  
  **Valid Values:** `"East US"`, `"North Europe"`, `"West Europe"`, `"Southeast Asia"`, `"Australia East"`, `"UK South"`, `"Canada Central"`, `"Central India"`, `"Japan East"`

- **`--status`**  
  Status of the iTwin. Defaults to Active.  
  **Type:** `iTwinStatus` **Required:** No  
  **Valid Values:** `"Active"`, `"Inactive"`, `"Trial"`

- **`--parentId`**  
  Optional parent iTwin Id. Defaults to user's Account iTwin.  
  **Type:** `string` **Required:** No

## Examples

```bash
# Example 1: Creating a basic iTwin with minimal required fields
itp itwin create --class "Infrastructure" --subClass "Bridge" --displayName "Golden Gate Revamp"

# Example 2: Creating an iTwin with geographic location and timezone
itp itwin create --class "Transportation" --subClass "Railway" --displayName "High-Speed Rail Project" --geographicLocation "San Francisco, CA" --ianaTimeZone "America/Los_Angeles"

# Example 3: Specifying a data center location
itp itwin create --class "Utilities" --subClass "Power Plant" --displayName "Solar Farm Expansion" --dataCenterLocation "UK South"
```

## API Reference

[Create iTwin](https://developer.bentley.com/apis/itwins/operations/create-itwin/)
