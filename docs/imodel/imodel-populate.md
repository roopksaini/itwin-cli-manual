# itwin-cli imodel populate

Synchronize design files into an iModel.

## Options

- **`--id`**  
  The ID of the iModel to populate.  
  **Type:** `string` **Required:** Yes

- **`--files`**  
  A list of source files to synchronize into the iModel. Separate multiple files with a space.  
  **Type:** `string`  **Required:** Yes

- **`--connectorTypes`**  
  A list of connectors to prioritize for synchronization. Separate multiple connectors with a space.
  **Type:** `string` **Required:** No  
  **Valid Values:** `"SHELLEDWCSV"`, `"CIVIL"`, `"MSTN"`, `"OBD"`, `"PROSTRUCTURES"`, `"AUTOPLANT"`, `"AVEVAPID"`, `"CIVIL3D"`, `"DWG"`, `"IFC"`, `"GEOSPATIAL"`, `"OPENTOWER"`, `"REVIT"`, `"SPPID"`, `"SPXREVIEW"`, `"AVEVADIAGRAMS"`, `"NWD"`, `"INTELLIPID"`, `"PSEXCEL"`

## Examples

```bash
# Example 1: Synchronizing DWG Files
itwin-cli imodel populate --id "b1a2c3d4-5678-90ab-cdef-1234567890ab" --files "file1.dwg file2.dwg" --connectorTypes "DWG"

# Example 2: Synchronizing DGN Files
itwin-cli imodel populate --id "c2d3e4f5-6789-01ab-cdef-2345678901bc" --files "site1.dgn structure2.dgn" --connectorTypes "CIVIL"

# Example 3: Synchronizing CSV and IFC Files
itwin-cli imodel populate --id "d3e4f5g6-7890-12ab-cdef-3456789012cd" --files "data1.csv data2.csv model.ifc"

# Example: Synchronizing Revit and DGN Files
itwin-cli imodel populate --id "i9j0k1l2-3456-78ab-cdef-9012345678ij" --files "model.rvt design.dgn"
```

## Workflow Reference

- [Synchronization](/docs/workflows/synchronization)
