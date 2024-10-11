# Track iTwin project progress

## Scenario

As a user, I want to monitor key aspects of my iTwin project at a glance. This includes tracking repositories, iModels, connections, synchronized files, user roles, changesets, and named versions in an iModel.

## Steps

1. **List repositories**: Track the repositories associated with the iTwin.
2. **List iModels**: Track all iModels within the iTwin.
3. **List connections and synchronized files**: Loop through all iModel connections and get the associated files for each connection.
4. **List changesets and named versions**: Monitor changesets and named versions to understand the history and progress of design updates.
5. **List user information**: Get all users, groups, and owners for the iTwin.

## Commands Used

- `itp itwin repository list`  
  Lists all repositories in the iTwin.

- `itp imodel list`  
  Lists all iModels associated with the iTwin.

- `itp imodel connection list`  
  Lists all connections for each iModel.

- `itp imodel connection sourcefile list`  
  Lists all source files in a connection.

- `itp imodel connection sourcefile info`  
  Retrieves information about a specific file.

- `itp imodel changeset list`  
  Lists all changesets for an iModel.

- `itp imodel named-version list`  
  Lists all named versions for an iModel.

- `itp access-control member user list`  
  Lists all users in the iTwin.

- `itp access-control member group list`  
  Lists all groups in the iTwin.

- `itp access-control member owner list`  
  Lists all owners in the iTwin.

## Script

```bash
#!/bin/bash

# iTwin and iModel IDs
ITWIN_ID="your-itwin-id"

# List all repositories in the iTwin
echo "Listing Repositories:"
itp itwin repository list --iTwinId $ITWIN_ID

# List all iModels in the iTwin
echo "Listing iModels:"
itp imodel list --iTwinId $ITWIN_ID

# For each iModel, perform additional tracking
IMODELS=$(itp imodel list --iTwinId $ITWIN_ID | jq -r '.iModels[].id')
for IMODEL_ID in $IMODELS; do
  echo "Tracking progress for iModel ID: $IMODEL_ID"
  
  # List all connections in the iModel
  echo "Listing Connections:"
  itp imodel connection list --iModelId $IMODEL_ID
  
  # Loop through all connections and list files for each connection
  echo "Listing Files for Each Connection:"
  CONNECTIONS=$(itp imodel connection list --iModelId $IMODEL_ID | jq -r '.connections[].id')
  for CONNECTION_ID in $CONNECTIONS; do
    echo "Files for Connection ID: $CONNECTION_ID"
    
    # Get the source files in this connection
    FILES=$(itp imodel connection sourcefile list --iModelId $IMODEL_ID --connectionId $CONNECTION_ID | jq -r '.files[].id')
    
    for FILE_ID in $FILES; do
      # Fetch info for each file to get the filename
      FILENAME=$(itp imodel connection sourcefile info --iModelId $IMODEL_ID --connectionId $CONNECTION_ID --fileId $FILE_ID | jq -r '.file.name')
      echo "File: $FILENAME (ID: $FILE_ID)"
    done
  done

  # List all changesets in the iModel
  echo "Listing Changesets:"
  itp imodel changeset list --iModelId $IMODEL_ID

  # List all named versions in the iModel
  echo "Listing Named Versions:"
  itp imodel named-version list --iModelId $IMODEL_ID
done

# List all users in the iTwin
echo "Listing Users:"
itp access-control member user list --iTwinId $ITWIN_ID

# List all groups in the iTwin
echo "Listing Groups:"
itp access-control member group list --iTwinId $ITWIN_ID

# List all owners in the iTwin
echo "Listing Owners:"
itp access-control member owner list --iTwinId $ITWIN_ID
```

## Expected Outcome

This script will give you a full snapshot of your project's current state, including:

- A complete list of repositories and iModels.
- Detailed information on all connections and synchronized files.
- A list of all changesets and named versions for the iModel.
- All users, groups, and owners involved in the iTwin.

## Next Steps

- **Logging**: Store the output in a log file for record-keeping and auditing.
- **Alerts**: Set up notifications when certain conditions are met, like when there are no new changesets or files in a given week.
- **Dashboard Integration**: Integrate the output with a dashboard to provide real-time project tracking.
