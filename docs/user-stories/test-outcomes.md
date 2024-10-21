# User Stories: Test Outcomes

### **Getting Started**

#### [Create and refine an iTwin](docs/user-stories/itwin-create.md)

- **Command**:
  ```bash
  ./itp.sh itwin create --class 'Thing' --subClass 'Asset' --displayName 'New Bridge Project' --geographicLocation 'Chandigarh, India'
  ```
  - **Result**: `Unknown commands: Bridge, Project, India`
  - **Issue**: Potential issue with processing spaces in options.

- **Command**:
  ```bash
  ./itp.sh itwin update --id '94e0332b-d84c-4b40-8858-737ffe9497cb' --geographicLocation 'Chandigarh, India'
  ```
  - **Result**: `Unknown command: India`
  - **Issue**: Processing spaces in options.

- **Command** (successful):
  ```bash
  ./itp.sh itwin create --class 'Thing' --subClass 'Asset' --displayName '123'
  ```
  - **Result**:
  ```json
  {
    "id": "94e0332b-d84c-4b40-8858-737ffe9497cb",
    "class": "Thing",
    "subClass": "Asset",
    "displayName": "123",
    "geographicLocation": null,
    "ianaTimeZone": null,
    "dataCenterLocation": "East US",
    "status": "Active"
  }
  ```

---

#### [Create and refine an iModel](docs/user-stories/imodel-create.md)

- **Command**:
  ```bash
  ./itp.sh imodel populate --id '6d98ed1f-ce51-4592-870d-55fabc225d39' --files './data/design/original/Architectural.dgn' --connectorTypes 'MSTN'
  ```
  - **Result**: `Error: HTTP error! status: 422. Response data: {"code":"InvalidStorageRequest","message":"Request payload contains errors.","details":[{"code":"InvalidValue","message":"Item contains invalid characters"}]}`
  - **Issue**: Parsing file paths.

- **Command**:
  ```bash
  ./itp.sh imodel populate --id '6d98ed1f-ce51-4592-870d-55fabc225d39' --files 'Architectural.dgn' --connectorTypes 'MSTN'
  ```
  - **Result**: `itp imodel connection auth | Authenticate connector for user | ReferenceError: open is not defined.`

- **Command** (successful):
  ```bash
  ./itp.sh imodel create --iTwinId "94e0332b-d84c-4b40-8858-737ffe9497cb" --name "123"
  ```
  - **Result**:
  ```json
  {
    "id": "6d98ed1f-ce51-4592-870d-55fabc225d39",
    "name": "123",
    "state": "initialized",
    "iTwinId": "94e0332b-d84c-4b40-8858-737ffe9497cb",
    "extent": null
  }
  ```

---

### **Working with Design Data**

#### [Populate an iModel with design data](docs/user-stories/imodel-populate-data.md)

- **Command**:
  ```bash
  ./itp.sh imodel populate --id '6d98ed1f-ce51-4592-870d-55fabc225d39' --files 'Architectural.dgn' --connectorTypes 'MSTN'
  ```
  - **Result**: `itp storage file upload | Unknown command: filename%3D"Architectural.dgn"`

---

#### [View changes between iModel versions](docs/user-stories/imodel-changeset-compare.md)

- **Command**:
  ```bash
  ./itp.sh changed-elements enable --iModelId '6d98ed1f-ce51-4592-870d-55fabc225d39'
  ```
  - **Result**: `TypeError: Cannot convert undefined or null to object`
  - **Issue**: Endpoint requires iTwinId (projectId). Option missing.

- **Success**: Enabled change tracking using API docs "Try it out" feature.

---

### **Collaboration and Permissions**

#### [Provide a group of users iTwin access](docs/user-stories/itwin-group-access.md)

- **Command**:
  ```bash
  ./itp.sh access-control group create --iTwinId "94e0332b-d84c-4b40-8858-737ffe9497cb" --name "Example Group"
  ```
  - **Result**: `Unknown command: Group`

---

#### [Add multiple owners to an iTwin](docs/user-stories/itwin-add-multiple-owners.md)

- **Command**:
  ```bash
  ./itp.sh access-control member owner add --iTwinId "94e0332b-d84c-4b40-8858-737ffe9497cb" --email "bas_eng_user1@mailinater.com"
  ```
  - **Result**: `Error: HTTP error! status: 404. Response data: {"code":"ResourceNotFound","message":"The requested resource was not found. Verify the API URL and the Accept header."}`

---

### **Repository Management**

#### [Add new repositories to an iTwin](docs/user-stories/itwin-add-repositories.md)

- **Command**:
  ```bash
  ./itp.sh itwin repository create --iTwinId "94e0332b-d84c-4b40-8858-737ffe9497cb" --class "Subsurface" --uri "https://example.com/subsurface-repo"
  ```
  - **Result**: `Error: HTTP error! status: 422. Response data: {"code":"InvalidiTwinsRequest","message":"Cannot add iTwin Repository.","details":[{"code":"InvalidValue","message":"SubClass value is incorrect."}]}`

  - **Issue**: Subclass might be required, despite API documentation saying it's optional.

- **Command** (successful):
  ```bash
  ./itp.sh itwin repository create --iTwinId "94e0332b-d84c-4b40-8858-737ffe9497cb" --class "GeographicInformationSystem" --subClass "WebMapService" --uri "https://example.com/gis-repo"
  ```
  - **Result**:
  ```json
  {
    "repository": {
      "id": "c349bed2-6a9e-44d5-8542-5c4b9461dcf8",
      "class": "GeographicInformationSystem",
      "subClass": "WebMapService",
      "uri": "https://example.com/gis-repo"
    }
  }
  ```

---

### **Automation and Scripting**

#### [Automate iModel updates with the latest design](docs/user-stories/imodel-automate-update.md)

#### [Track iTwin project progress](docs/user-stories/itwin-script-progress-tracker.md)

---

### **Storage and Versioning**

#### [Upload project PDFs to iTwin storage](docs/user-stories/itwin-upload-files-storage.md)

#### [Create an iModel named version](docs/user-stories/imodel-create-named-version.md)

---

### Common Issues

- **Commands not processing spaces**: Encountered issues where spaces in option values were not processed correctly, causing unknown command errors.
- **Missing or incorrect endpoints**: Some commands resulted in 404 errors, likely due to incorrect or missing endpoints.
