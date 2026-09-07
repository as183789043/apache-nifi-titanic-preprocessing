# Apache NiFi Titanic Preprocessing Playground

A hands-on Apache NiFi data pipeline demonstrating record processing (CSV to JSON), content transformations, attribute extraction, and dynamic record routing using the Titanic dataset.

---

## 🏗️ Architecture & Pipeline Overview

### Process Group Architecture
<img width="1999" height="831" alt="Process Group Overview" src="https://github.com/user-attachments/assets/cddd5444-950f-494f-9037-20cb1e8c67ea" />

### Data Flow Execution
<img width="1215" height="790" alt="Data Flow Pipeline" src="https://github.com/user-attachments/assets/f56dbc99-36eb-4433-93cd-2fa23e673386" />

### Processing Logic
<img width="1286" height="800" alt="Processor Logic Detail" src="https://github.com/user-attachments/assets/d8058e40-c9ff-4efd-b713-91b419d5668e" />

---

## 🚀 How to Replicate This Pipeline

### Prerequisites
* Apache NiFi **2.x** instance
* Download the flow definition file (`.json`) and the test dataset (`train.csv`) from this repository.

### Step 1: Create an Empty Process Group
Drag a **Process Group** component onto the NiFi canvas and give it a name.
<img width="1762" height="875" alt="Create Process Group" src="https://github.com/user-attachments/assets/640d7bf9-ec13-42bf-913a-7a9eaf534057" />

### Step 2: Import the Flow Definition
Upload the downloaded `.json` definition file into the newly created Process Group.
<img width="1072" height="678" alt="Import Flow Definition" src="https://github.com/user-attachments/assets/8328c2d1-8a6f-420e-a20b-5269a6672fd7" />

### Step 3: Configure File Paths & Controller Services
Open the `GetFile` / `ListFile` processor configuration and ensure the input directory matches your local system's `train.csv` path (e.g., `/tmp/data/`). Ensure `CSVReader` and `JsonRecordSetWriter` are enabled.
<img width="1263" height="733" alt="Configure Processor Path" src="https://github.com/user-attachments/assets/e596e9b3-d1d8-461f-bdda-bf375e94842e" />

---

## 🔍 Key NiFi Features Demonstrated

* **Data Lineage (Data Provenance)**: Track end-to-end data processing events and transformations for complete visibility.
<img width="1967" height="972" alt="Data Lineage View" src="https://github.com/user-attachments/assets/20c2bf1b-b7cc-4712-a052-aa6f33f08380" />

* **Attribute Extraction (Metadata Header Management)**: Extract content values into FlowFile attributes via `EvaluateJsonPath` for downstream routing decision-making.
<img width="1975" height="883" alt="FlowFile Attributes" src="https://github.com/user-attachments/assets/26cfbb8b-a020-44ea-90d5-17db5627bb0d" />

* **Content Mutation (Payload Transformation)**: Perform field mapping and binary conversions (`Sex`: `male/female` -> `1/0`) using `UpdateRecord`.
<img width="1982" height="617" alt="FlowFile Content View" src="https://github.com/user-attachments/assets/0e335095-92c0-4bf1-9da5-2471df61c523" />
