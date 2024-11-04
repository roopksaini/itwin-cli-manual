# User Stories: Test Outcomes

### **Getting Started**

#### [Create and refine an iTwin](user-stories/itwin-create.md)

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

- **Command**:
  ```bash
  ./itp.sh itwin create --class 'Thing' --subClass 'Asset' --displayName '123'
  ```
  - **Result** (successful):
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

#### [Create and refine an iModel](user-stories/imodel-create.md)

- **Command**:
  ```bash
  ./itp.sh imodel create --iTwinId "94e0332b-d84c-4b40-8858-737ffe9497cb" --name "123"
  ```
  - **Result** (successful):
  ```json
  {
    "id": "6d98ed1f-ce51-4592-870d-55fabc225d39",
    "name": "123",
    "state": "initialized",
    "iTwinId": "94e0332b-d84c-4b40-8858-737ffe9497cb",
    "extent": null
  }
  ```

- **Command**:
  ```bash
  ./itp.sh imodel create --iTwinId "94e0332b-d84c-4b40-8858-737ffe9497cb" --name "123" --extent '{"southWest":{"latitude":34,"longitude":-118},"northEast":{"latitude":34,"longitude":-118}}
 ```

  - **Result** (successful):
  ```json
  {
    "id": "6d98ed1f-ce51-4592-870d-55fabc225d39",
    "displayName": "123",
    "dataCenterLocation": "East US",
    "name": "123",
    "description": null,
    "state": "initialized",
    "createdDateTime": "2024-10-17T13:44:55.5370000Z",
    "iTwinId": "94e0332b-d84c-4b40-8858-737ffe9497cb",
    "isSecured": false,
    "extent": {
      "southWest": {
        "latitude": 34,
        "longitude": -118
      },
      "northEast": {
        "latitude": 34,
        "longitude": -118
      }
    },
    "containersEnabled": 0,
    "_links": {
      "creator": {
        "href": "https://api.bentley.com/imodels/6d98ed1f-ce51-4592-870d-55fabc225d39/users/6ba725bc-aca9-4315-8d02-909297e9e819"
      },
      "changesets": {
        "href": "https://api.bentley.com/imodels/6d98ed1f-ce51-4592-870d-55fabc225d39/changesets"
      },
      "namedVersions": {
        "href": "https://api.bentley.com/imodels/6d98ed1f-ce51-4592-870d-55fabc225d39/namedversions"
      },
      "upload": null,
      "complete": null
    }
  }
  ```

- **Command**:
  ```bash
./itp.sh imodel update --id "6d98ed1f-ce51-4592-870d-55fabc225d39" --extent '{"southWest":{"latitude":34.052235,"longitude":-118.243683},"northEast":{"latitude":34.252235,"longitude":-118.443683}}'
 ```

  - **Result** (successful):
  ```json
  {
    "id": "6d98ed1f-ce51-4592-870d-55fabc225d39",
    "displayName": "123",
    "dataCenterLocation": "East US",
    "name": "123",
    "description": null,
    "state": "initialized",
    "createdDateTime": "2024-10-17T13:44:55.5370000Z",
    "iTwinId": "94e0332b-d84c-4b40-8858-737ffe9497cb",
    "isSecured": false,
    "extent": {
      "southWest": {
        "latitude": 34.052235,
        "longitude": -118.243683
      },
      "northEast": {
        "latitude": 34.252235,
        "longitude": -118.443683
      }
    },
    "containersEnabled": 0,
    "_links": {
      "creator": {
        "href": "https://api.bentley.com/imodels/6d98ed1f-ce51-4592-870d-55fabc225d39/users/6ba725bc-aca9-4315-8d02-909297e9e819"
      },
      "changesets": {
        "href": "https://api.bentley.com/imodels/6d98ed1f-ce51-4592-870d-55fabc225d39/changesets"
      },
      "namedVersions": {
        "href": "https://api.bentley.com/imodels/6d98ed1f-ce51-4592-870d-55fabc225d39/namedversions"
      }
    }
  }
  ```

---

### **Working with Design Data**

#### [Populate an iModel with design data](user-stories/imodel-populate-data.md)

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

- **Command**:
  ```bash
  ./itp.sh imodel populate --id '6d98ed1f-ce51-4592-870d-55fabc225d39' --files 'Architectural.dgn' --connectorTypes 'MSTN'
  ```
  - **Result**: `itp storage file upload | Unknown command: filename%3D"Architectural.dgn"`

---

#### [View changes between iModel versions](user-stories/imodel-changeset-compare.md)

- **Command**:
  ```bash
  ./itp.sh changed-elements enable --iModelId '6d98ed1f-ce51-4592-870d-55fabc225d39'
  ```
  - **Result**: `TypeError: Cannot convert undefined or null to object`
  - **Issue**: Endpoint requires iTwinId (projectId). Option missing.

- **Success**: Enabled change tracking using API docs "Try it out" feature.

---

### **Collaboration and Permissions**

#### [Provide a group of users iTwin access](user-stories/itwin-group-access.md)

- **Command**:
  ```bash
  ./itp.sh access-control group create --iTwinId "94e0332b-d84c-4b40-8858-737ffe9497cb" --name "Example Group"
  ```
  - **Result**: `Unknown command: Group`

---

#### [Add multiple owners to an iTwin](user-stories/itwin-add-multiple-owners.md)

- **Command**:
  ```bash
  ./itp.sh access-control member owner add --iTwinId "94e0332b-d84c-4b40-8858-737ffe9497cb" --email "bas_eng_user1@mailinater.com"
  ```
  - **Result**: `Error: HTTP error! status: 404. Response data: {"code":"ResourceNotFound","message":"The requested resource was not found. Verify the API URL and the Accept header."}`

---

### **Repository Management**

#### [Add new repositories to an iTwin](user-stories/itwin-add-repositories.md)

- **Command**:
  ```bash
  ./itp.sh itwin repository create --iTwinId "94e0332b-d84c-4b40-8858-737ffe9497cb" --class "Subsurface" --uri "https://example.com/subsurface-repo"
  ```
  - **Result**: `Error: HTTP error! status: 422. Response data: {"code":"InvalidiTwinsRequest","message":"Cannot add iTwin Repository.","details":[{"code":"InvalidValue","message":"SubClass value is incorrect."}]}`

  - **Issue**: Subclass might be required, despite API documentation saying it's optional.

- **Command**:
  ```bash
  ./itp.sh itwin repository create --iTwinId "94e0332b-d84c-4b40-8858-737ffe9497cb" --class "GeographicInformationSystem" --subClass "WebMapService" --uri "https://example.com/gis-repo"
  ```
  - **Result** (successful):
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

#### [Automate iModel updates with the latest design](user-stories/imodel-automate-update.md)

#### [Track iTwin project progress](user-stories/itwin-script-progress-tracker.md)

---

### **Storage and Versioning**

#### [Upload project PDFs to iTwin storage](user-stories/itwin-upload-files-storage.md)

- **Command**:
  ```bash
  ./itp.sh storage root-folder --iTwinId "94e0332b-d84c-4b40-8858-737ffe9497cb"
  ```
  - **Result** (successful):
  ```json
  {
    "items": [
      {
        "size": 5710336,
        "isFileLocked": false,
        "type": "file",
        "id": "KzPglEzYQEuIWHN__pSXy70KXHckjO1LrITSu2LZ__k",
        "displayName": "Architectural.dgn",
        "description": null,
        "path": "Architectural.dgn",
        "lastModifiedByDisplayName": "Roop Saini",
        "createdDateTime": "2024-10-18T07:57:42.5914518Z",
        "lastModifiedDateTime": "2024-10-18T07:57:42.5914549Z",
        "parentFolderId": "KzPglEzYQEuIWHN__pSXyysz4JRM2EBLiFhzf_6Ul8s",
        "_links": {
          "createdBy": {
            "href": "https://api.bentley.com/accesscontrol/itwins/94e0332b-d84c-4b40-8858-737ffe9497cb/members/6ba725bc-aca9-4315-8d02-909297e9e819"
          },
          "lastModifiedBy": {
            "href": "https://api.bentley.com/accesscontrol/itwins/94e0332b-d84c-4b40-8858-737ffe9497cb/members/6ba725bc-aca9-4315-8d02-909297e9e819"
          },
          "parentFolder": {
            "href": "https://api.bentley.com/storage/folders/KzPglEzYQEuIWHN__pSXyysz4JRM2EBLiFhzf_6Ul8s"
          }
        }
      }
    ],
    "_links": {
      "self": {
        "href": "https://api.bentley.com/storage?iTwinId=94e0332b-d84c-4b40-8858-737ffe9497cb&$top=100&$skip=0"
      },
      "prev": {
        "href": "https://api.bentley.com/storage?iTwinId=94e0332b-d84c-4b40-8858-737ffe9497cb&$top=100&$skip=0"
      },
      "next": {
        "href": "https://api.bentley.com/storage?iTwinId=94e0332b-d84c-4b40-8858-737ffe9497cb&$top=100&$skip=100"
      },
      "folder": {
        "href": "https://api.bentley.com/storage/folders/KzPglEzYQEuIWHN__pSXyysz4JRM2EBLiFhzf_6Ul8s"
      }
    }
  }
  ```

  - **Command**:
  ```bash
  ./itp.sh storage folder create --parentFolderId "KzPglEzYQEuIWHN__pSXyysz4JRM2EBLiFhzf_6Ul8s" --displayName "FloorPlans"
  ```
  - **Result** (successful):
  ```json
  {
    "type": "folder",
    "id": "KzPglEzYQEuIWHN__pSXy7l7buGqtw5Hlcr9tDl5JcA",
    "displayName": "FloorPlans",
    "description": null,
    "path": "FloorPlans",
    "lastModifiedByDisplayName": "Roop Saini",
    "createdDateTime": "2024-10-28T09:52:04.0688377Z",
    "lastModifiedDateTime": "2024-10-28T09:52:04.0688403Z",
    "parentFolderId": "KzPglEzYQEuIWHN__pSXyysz4JRM2EBLiFhzf_6Ul8s",
    "_links": {
      "createdBy": {
        "href": "https://api.bentley.com/accesscontrol/itwins/94e0332b-d84c-4b40-8858-737ffe9497cb/members/6ba725bc-aca9-4315-8d02-909297e9e819"
      },
      "lastModifiedBy": {
        "href": "https://api.bentley.com/accesscontrol/itwins/94e0332b-d84c-4b40-8858-737ffe9497cb/members/6ba725bc-aca9-4315-8d02-909297e9e819"
      },
      "parentFolder": {
        "href": "https://api.bentley.com/storage/folders/KzPglEzYQEuIWHN__pSXyysz4JRM2EBLiFhzf_6Ul8s"
      }
    }
  }
  ```



  - **Command**:
  ```bash
  ./itp.sh storage file create --folderId "KzPglEzYQEuIWHN__pSXy7l7buGqtw5Hlcr9tDl5JcA" --displayName "floorplan.pdf"
  ```
  - **Result** (successful):
  ```json
  {
    "_links": {
      "completeUrl": {
        "href": "https://api.bentley.com/storage/files/KzPglEzYQEuIWHN__pSXyyuNRpJQq-BEjRogaS-9eBQ/complete"
      },
      "uploadUrl": {
        "href": "https://projectshareprodeussa01.blob.core.windows.net/azuresqldbecpluginstorage/ProjectShare/File/92468d2b-ab50-44e0-8d1a-20692fbd7814?sv=2019-07-07&sr=b&sig=ck9KEdo0jecQfl%2BW5iT0%2Bs5KR8YLhkjhzAHJ1LSX%2BLo%3D&se=2024-10-28T11%3A46%3A27Z&sp=rw&rscd=attachment%3B%20filename%3D%22floorplan.pdf%22"
      }
    }
  }
  ```


  - **Command**:
  ```bash
  ./itp.sh storage file upload --uploadUrl "https://projectshareprodeussa01.blob.core.windows.net/azuresqldbecpluginstorage/ProjectShare/File/92468d2b-ab50-44e0-8d1a-20692fbd7814?sv=2019-07-07&sr=b&sig=ck9KEdo0jecQfl%2BW5iT0%2Bs5KR8YLhkjhzAHJ1LSX%2BLo%3D&se=2024-10-28T11%3A46%3A27Z&sp=rw&rscd=attachment%3B%20filename%3D%22floorplan.pdf%22" --filePath "floorplan.pdf"
```
  - **Result** (successful):
  ```json
  {}
  ```

  - **Command**:
  ```bash
  ./itp.sh storage file update-complete --fileId "KzPglEzYQEuIWHN__pSXyyuNRpJQq-BEjRogaS-9eBQ"
  ```
  - **Result** (successful):
  ```json
  {
    "file": {
      "size": 1634286,
      "isFileLocked": false,
      "type": "file",
      "id": "KzPglEzYQEuIWHN__pSXyyuNRpJQq-BEjRogaS-9eBQ",
      "displayName": "floorplan.pdf",
      "description": null,
      "path": "FloorPlans/floorplan.pdf",
      "lastModifiedByDisplayName": "Roop Saini",
      "createdDateTime": "2024-10-28T10:46:27.4390048Z",
      "lastModifiedDateTime": "2024-10-28T10:46:27.4390069Z",
      "parentFolderId": "KzPglEzYQEuIWHN__pSXy7l7buGqtw5Hlcr9tDl5JcA",
      "_links": {
        "createdBy": {
          "href": "https://api.bentley.com/accesscontrol/itwins/94e0332b-d84c-4b40-8858-737ffe9497cb/members/6ba725bc-aca9-4315-8d02-909297e9e819"
        },
        "lastModifiedBy": {
          "href": "https://api.bentley.com/accesscontrol/itwins/94e0332b-d84c-4b40-8858-737ffe9497cb/members/6ba725bc-aca9-4315-8d02-909297e9e819"
        },
        "parentFolder": {
          "href": "https://api.bentley.com/storage/folders/KzPglEzYQEuIWHN__pSXy7l7buGqtw5Hlcr9tDl5JcA"
        }
      }
    }
  }
  ```

  - **Command**:
  ```bash
  ./itp.sh storage file list --folderId "KzPglEzYQEuIWHN__pSXy7l7buGqtw5Hlcr9tDl5JcA"
  ```
  - **Result** (successful):
  ```json
  [
    {
      "size": 1634286,
      "isFileLocked": false,
      "type": "file",
      "id": "KzPglEzYQEuIWHN__pSXyyuNRpJQq-BEjRogaS-9eBQ",
      "displayName": "floorplan.pdf",
      "description": null,
      "path": "FloorPlans/floorplan.pdf",
      "lastModifiedByDisplayName": "Roop Saini",
      "createdDateTime": "2024-10-28T10:46:27.4390048Z",
      "lastModifiedDateTime": "2024-10-28T10:46:27.4390069Z",
      "parentFolderId": "KzPglEzYQEuIWHN__pSXy7l7buGqtw5Hlcr9tDl5JcA",
      "_links": {
        "createdBy": {
          "href": "https://api.bentley.com/accesscontrol/itwins/94e0332b-d84c-4b40-8858-737ffe9497cb/members/6ba725bc-aca9-4315-8d02-909297e9e819"
        },
        "lastModifiedBy": {
          "href": "https://api.bentley.com/accesscontrol/itwins/94e0332b-d84c-4b40-8858-737ffe9497cb/members/6ba725bc-aca9-4315-8d02-909297e9e819"
        },
        "parentFolder": {
          "href": "https://api.bentley.com/storage/folders/KzPglEzYQEuIWHN__pSXy7l7buGqtw5Hlcr9tDl5JcA"
        }
      }
    }
  ]
  ```

#### [Create an iModel named version](user-stories/imodel-create-named-version.md)

---

### Common Issues

- **Commands not processing spaces**: Encountered issues where spaces in option values were not processed correctly, causing unknown command errors.
- **Missing or incorrect endpoints**: Some commands resulted in 404 errors, likely due to incorrect or missing endpoints.
