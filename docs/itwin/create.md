# itp itwin create

Create a new iTwin with specified properties.

## Options

- **`--class`**  
  The Class of your iTwin.  
  **Type:** `string` **Required:** Yes  
  **Valid Values:** `"Account"`, `"Thing"`, `"Endeavor"`

- **`--subClass`**  
  The subClass of your iTwin.  
  **Type:** `string` **Required:** Yes  
  **Valid Values:** `"Account"`, `"Portfolio"`, `"Asset"`, `"Program"`, `"Project"`, `"WorkPackage"`

- **`--displayName`**  
  The iTwin's display name.  
  **Type:** `string` **Required:** Yes

- **`--type`**  
  Open ended property to define your iTwin's type.  
  **Type:** `string` **Required:** No

- **`--number`**  
  Unique identifier for the iTwin. Defaults to iTwin Id if unspecified.  
  **Type:** `string` **Required:** No

- **`--geographicLocation`**  
  Optional location, typically an address or city.  
  **Type:** `string` **Required:** No

- **`--ianaTimeZone`**  
  Optional IANA time zone ID.  
  **Type:** `string` **Required:** No

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
itp itwin create --class "Thing" --subClass "Project" --displayName "Golden Gate Revamp"

# Example 2: Creating an iTwin with geographic location and timezone
itp itwin create --class "Endeavor" --subClass "Asset" --displayName "High-Speed Rail Project" --geographicLocation "San Francisco, CA" --ianaTimeZone "America/Los_Angeles"

# Example 3: Specifying a data center location
itp itwin create --class "Account" --subClass "Portfolio" --displayName "Solar Farm Expansion" --dataCenterLocation "UK South"
```

## API Reference

[Create iTwin](https://developer.bentley.com/apis/itwins/operations/create-itwin/)
