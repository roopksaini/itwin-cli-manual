# Create and refine an iTwin

## Scenario

As a user, I want to quickly create an iTwin and start working on my project, even if I don’t have all the details immediately. Over time, as I gather more information about the project’s class, subclass, location, and time zone, I can refine the iTwin by updating its properties, ensuring it better reflects the project's scope and needs.

## Steps

1. **Create an iTwin**: Start by creating an iTwin with the required class and subclass to define its basic structure.
2. **Start working on the project**: You can start managing project data and working within the iTwin, even before all additional properties (such as geographic location) are defined.
3. **Update the iTwin properties later**: As you learn more about the project (e.g., location, data center), update the iTwin with these details for better alignment with project requirements.

## Commands Used

- `itp itwin create`  
  Creates a new iTwin with basic properties.

- `itp itwin update`  
  Updates the iTwin's properties as the project progresses.

## Example

**Step 1: Create an iTwin with class and subclass**
```bash
itp itwin create --class "Thing" --subClass "Asset" --displayName "New Bridge Project"
```

**Step 2: Update the iTwin’s geographic location**
```bash
itp itwin update --iTwinId "your-itwin-id" --geographicLocation "San Francisco, CA"
```

**Step 3: Update the iTwin’s data center and status**
```bash
itp itwin update --iTwinId "your-itwin-id" --dataCenterLocation "UK South" --status "Active"
```

**Step 4: Update the iTwin’s time zone**
```bash
itp itwin update --iTwinId "your-itwin-id" --ianaTimeZone "America/Los_Angeles"
```

## Expected Outcome

By following these steps, you will have quickly created an iTwin and started work on your project. Over time, you can refine the iTwin by adding details such as geographic location, data center, and other relevant properties to better suit the project’s scope.

## Next Steps

- **Add Repositories and Members**: As the iTwin grows in complexity, consider adding repositories, assigning roles, and granting access to project members.
