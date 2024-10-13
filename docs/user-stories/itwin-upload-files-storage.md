# Uploading project PDFs to iTwin storage

## Scenario

As a user, I want to upload project-related PDFs, like floor plans, to iTwin storage by accessing the root folder, setting up a dedicated "floor plans" folder, uploading the PDF, and then confirming that it’s successfully stored by checking the folder contents.

## Steps

1. **Create an iTwin**: Start by creating a new iTwin for managing the project.
2. **Get the root folder**: Retrieve the root folder of the iTwin storage where you will create the new folder.
3. **Create a folder called “floor plans”**: Add a new folder specifically for storing floor plan PDFs.
4. **Upload the floorplan.pdf**: Upload the PDF file into the "floor plans" folder.
5. **Confirm the upload**: View the folder contents to ensure the PDF was uploaded successfully.

## Commands Used

- `itp itwin create`  
  Creates a new iTwin.

- `itp storage root-folder`  
  Retrieves the root folder for the iTwin’s storage.

- `itp storage folder create`  
  Creates a new folder in the iTwin’s storage.

- `itp storage file create`  
  Uploads a file (e.g., PDF) to the specified folder.

- `itp storage file list`  
  Lists the contents of a folder to confirm that the upload was successful.

## Example

**Step 1: Create an iTwin**
```bash
itp itwin create --displayName "New Project" --description "iTwin for uploading floor plans"
```

**Step 2: Get the root folder**
```bash
itp storage root-folder --iTwinId "your-itwin-id"
```

**Step 3: Create a folder called "floor plans"**
```bash
itp storage folder create --iTwinId "your-itwin-id" --parentId "root-folder-id" --displayName "Floor Plans"
```

**Step 4: Upload the floorplan.pdf**
```bash
itp storage file create --iTwinId "your-itwin-id" --folderId "your-folder-id" --filePath "/path/to/floorplan.pdf"
```

**Step 5: Confirm the upload by viewing the folder contents**
```bash
itp storage file list --iTwinId "your-itwin-id" --folderId "your-folder-id"
```

## Expected Outcome

By following these steps, you will have created an iTwin, organized a "floor plans" folder in the iTwin’s storage, uploaded the floorplan PDF, and confirmed the upload by viewing the folder's contents.

## Next Steps

- **Manage Project Documents**: Continue uploading, organizing, and managing additional project documents as needed.
