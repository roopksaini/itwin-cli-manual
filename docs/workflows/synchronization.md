# Synchronization

Workflow steps:

1. Get root folder of iTwin Storage.
2. Create file metadata in root folder using folder ID. Capture file ID.
3. Upload actual file data into the file.
4. Complete file upload. Confirmation step.
5. Create a new storage connection. Add file (using file ID from step 2).
6. Run storage connection.
7. Get storage connection recursively until final status is obtained.
8. Print synchronization status.