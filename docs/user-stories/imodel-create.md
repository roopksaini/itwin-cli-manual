# Create and refine an iModel

## Scenario

As a user, I want to create an iModel for a new project, initially set its extents, and then populate it with design data. After visualizing the data, I realize that the geographic extents are not sufficient, so I will update and expand the extents to capture the full scope of the project.

*Note: Setting the extents is optional when creating an iModel. In this user story, we are demonstrating how you can adjust extents based on feedback after visualizing the iModel.*

## Steps

1. **Create an iModel with initial extents**: Start by creating the iModel with basic details, including an initial geographic extent.
2. **Populate the iModel with design data**: Upload the design files to the iModel to visualize the progress.
3. **Visualize the iModel**: Use a visualization tool to inspect the iModel and realize that the current extents don't capture all the design data.
4. **Refine the iModel by expanding the extents**: Update the iModel’s extents to fully capture the design data and ensure it fits the project's geographic scope.

## Commands Used

- `itp imodel create`  
  Initializes a new iModel with basic properties and initial extents.

- `itp imodel populate`  
  Populates the iModel with design data.

- `itp imodel update`  
  Updates the iModel’s extents after realizing they were too small.

## Example

**Step 1: Create an iModel with initial extents**
```bash
itp imodel create --iTwinId "your-itwin-id" --name "New Infrastructure Project" --extent '{
  "southWest": {
    "latitude": 34.052235,
    "longitude": -118.243683
  },
  "northEast": {
    "latitude": 34.152235,
    "longitude": -118.343683
  }
}'
```

**Step 2: Populate the iModel with design data**
```bash
itp imodel populate --id "your-imodel-id" --files "file1.dwg file2.dwg" --connectorTypes "DWG"
```

**Step 3: Visualize the iModel**  
_Note: Use a visualization tool (external) to check the design data. After realizing the extents don’t cover the full area, proceed to Step 4._

**Step 4: Refine the iModel by expanding the extents**
```bash
itp imodel update --iModelId "your-imodel-id" --extent '{
  "southWest": {
    "latitude": 34.052235,
    "longitude": -118.243683
  },
  "northEast": {
    "latitude": 34.252235,
    "longitude": -118.443683
  }
}'
```

## Expected Outcome

By following these steps, you will have created and populated an iModel. After realizing the geographic extents were insufficient, you’ll have refined them to capture the full scope of the project data.

## Next Steps

- **Continue working with the iModel**: As more design data is added, visualize and further refine the iModel to fit the project needs.
