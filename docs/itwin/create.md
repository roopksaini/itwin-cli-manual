# itp itwin create

Create a new iTwin with specified properties.

## Options

- **`--class`**  
  The Class of your iTwin.  
  **Type:** `string` **Required:** Yes  
  **Valid Values:** `"Thing"`, `"Endeavor"`, `"Account"`

- **`--subClass`**  
  The subClass of your iTwin. Must match the selected class.  
  **Type:** `string` **Required:** Yes  
  **Valid Combinations:**  
  - For **`Thing`**: `"Asset"`, `"Portfolio"`  
  - For **`Endeavor`**: `"Project"`, `"Program"`, `"WorkPackage"`  
  - For **`Account`**: `"Account"`

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
# Example 1: Creating an iTwin with the 'Thing' class and 'Asset' subclass
itp itwin create --class "Thing" --subClass "Asset" --displayName "Golden Gate Revamp"

# Example 2: Creating an iTwin with the 'Endeavor' class and 'Project' subclass
itp itwin create --class "Endeavor" --subClass "Project" --displayName "Bridge Construction" --geographicLocation "San Francisco, CA" --ianaTimeZone "America/Los_Angeles"

# Example 3: Creating an iTwin with data center location and status set to 'Trial'
itp itwin create --class "Endeavor" --subClass "Program" --displayName "Rail Network" --dataCenterLocation "UK South" --status "Trial"
```

## API Reference

[Create iTwin](https://developer.bentley.com/apis/itwins/operations/create-itwin/)
