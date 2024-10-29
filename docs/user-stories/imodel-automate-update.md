# Automate iModel updates with latest design

## Scenario

As a user, I want to automatically update an iModel with the latest design files whenever I save design data on my local file system. The script will monitor the directory for file changes and trigger the update process in real time.

## Steps

1. **Create an iTwin and iModel**: Set up an iTwin and iModel for managing design data.
2. **Store directory and file(s) as constants**: Define the directory and files that will be monitored for changes.
3. **Populate the iModel**: Synchronize the initial design files into the iModel.
4. **Listen to file system events**: Use native or external libraries to monitor the directory for file updates.
5. **Trigger script on file changes**: When a design file is updated, execute the iModel update script.

## Commands Used

- `itp itwin create`  
  Creates a new iTwin.

- `itp imodel create`  
  Creates a new iModel within the iTwin.

- `itp imodel populate`  
  Synchronizes design files into the iModel.

## Example

**Step 1: Create an iTwin**
```bash
itp itwin create --class "Thing" --subClass "Asset" --displayName "New Infrastructure Project" --description "iTwin of new infrastructure project"
```

**Step 2: Create an iModel**
```bash
itp imodel create --iTwinId "your-itwin-id" --displayName "Building Design" --description "iModel for design updates"
```

**Step 3: Populate the iModel with initial design data**
```bash
itp imodel populate --id "your-imodel-id" --files "initial-design.dwg" --connectorTypes "DWG"
```

**Step 4: Define constants in the script**
```bash
#!/bin/bash

# Define the directory and files to watch
WATCH_DIR="/path/to/design/files"
FILE_PATHS="file1.dwg file2.dgn"
IMODEL_ID="your-imodel-id"
```

**Step 5: Monitor file system events (cross-platform)**

#### Linux/MacOS Solution (using `inotifywait`)

1. Install `inotify-tools` if you don't have it:

   - **Linux**:
     ```bash
     sudo apt-get install inotify-tools
     ```

   - **macOS** (via Homebrew):
     ```bash
     brew install inotify-tools
     ```

2. Set up the script to watch the directory for file changes:

```bash
#!/bin/bash

WATCH_DIR="/path/to/design/files"
IMODEL_ID="your-imodel-id"

# Monitor directory and trigger iModel update on file modification
inotifywait -m -e modify "$WATCH_DIR" |
while read -r directory events filename; do
  echo "Detected change in $filename, updating iModel..."
  itp imodel populate --id "$IMODEL_ID" --files "$WATCH_DIR/$filename"
done
```

#### Windows Solution (using PowerShell)

```powershell
# Define variables
$watchDir = "C:\path\to\design\files"
$iModelId = "your-imodel-id"

# Create FileSystemWatcher
$watcher = New-Object IO.FileSystemWatcher $watchDir
$watcher.EnableRaisingEvents = $true

# Define the action when a change is detected
$action = {
    $file = $Event.SourceEventArgs.FullPath
    Write-Host "Detected change in $file, updating iModel..."
    itp imodel populate --id $iModelId --files $file
}

# Register event handlers
Register-ObjectEvent $watcher 'Changed' -Action $action

# Keep the script running
while ($true) { Start-Sleep 1 }
```

#### Node.js Solution (Cross-platform)

1. Install **Node.js** and **chokidar**:
```bash
npm install chokidar
```

2. Create a simple **Node.js** script to monitor the directory:
```js
const chokidar = require('chokidar');
const { exec } = require('child_process');
const watchDir = '/path/to/design/files';
const iModelId = 'your-imodel-id';
```

3. Initialize the watcher
```js
chokidar.watch(watchDir).on('change', (path) => {
  console.log(`File ${path} has been changed, updating iModel...`);
  exec(`itp imodel populate --id ${iModelId} --files "${path}"`, (err, stdout, stderr) => {
    if (err) {
      console.error(`Error updating iModel: ${stderr}`);
      return;
    }
    console.log(`iModel updated successfully: ${stdout}`);
  });
});
```

## Expected Outcome

By following these steps, you will have a script that listens for file changes in a specific directory and automatically updates the iModel with the latest design files whenever changes are detected.

## Next Steps

- **Extend Monitoring**: You can expand the monitoring process to cover multiple directories or different types of design files as your project evolves.
