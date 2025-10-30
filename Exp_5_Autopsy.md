# Ex. No 5: Use Autopsy to Create a Case and Import Evidence

---

## Aim
To perform a forensic investigation using **Autopsy**, by creating a case, importing evidence, analyzing artifacts, and generating a forensic report.

---

## 📝 Steps

### Step 1: Installation
- **Download & Install** Autopsy from the [official website](https://www.autopsy.com/).  
- Follow installation instructions for your OS (Windows/Linux/macOS).  

---

### Step 2: Starting a New Case
- Open **Autopsy**.  
- Click **New Case**.
<br>
  <img width="500" alt="image" src="https://github.com/user-attachments/assets/2a20e0d8-508c-4829-8ac6-7598d6dd5642" />
<br>

- Enter:
  - Case name  
  - Case location (storage path)  
  - Case number, examiner’s name, etc.  
- Click **Next** to proceed.

<br>
<img width="500" alt="image" src="https://github.com/user-attachments/assets/635ac98b-95d5-441a-85df-b25b39fa920e" />
<br>
<img width="500" alt="image" src="https://github.com/user-attachments/assets/a6df0624-d439-4187-a8ea-583dee97da7e" />
<br>

---

### Step 3: Adding a Data Source
- After creating a case, Autopsy will prompt you to add a **data source**.  
- Choose the source type:
  - Disk images (`.E01`, `.dd`, `.raw`)  
  - Directories  
  - Logical files  
  - Local disks  
- Browse and select the image file (e.g., `4Dell Latitude CPi.E01`, `4Dell Latitude CPi.E02`).
  <br>
  <img width="500" alt="image" src="https://github.com/user-attachments/assets/c0481c08-433e-405e-b524-dc7327e6351a" />
  <br>
- **Configure Ingest Modules**:
  - File Type Identification  
  - Keyword Search  
  - Hash Lookup  
  - (Enable/disable as per requirement)  
- Click **Next** to start the analysis.
  <br>
  <img width="500" alt="image" src="https://github.com/user-attachments/assets/06a0b5a4-d4b3-4e97-a350-c1e6b16f2263" />
  <br>

---

### Step 4: Initial Analysis & Overview
- **Ingest Progress**: Progress is shown in the lower-left corner.  
- **Artifacts Categorization**:
  - File system metadata  
  - Web artifacts  
  - Communication records  
- **Tree Viewer**: Navigate through File System, Web History, Email, etc.
  <br>
  <img width="500" alt="image" src="https://github.com/user-attachments/assets/0b3245db-9acb-49be-bf2a-5107f262a3df" />
  <br>

---

### Step 5: Detailed Analysis
- **Keyword Search**: Use pre-configured or custom keyword lists.  
- **File Analysis**: Open, preview, or export files.  
- **Timeline Analysis**: Visualize user activity across time.  
- **Hash Analysis**: Compare with known hash databases (good/bad files).
<br>
<img width="500" alt="image" src="https://github.com/user-attachments/assets/7f3193bf-6ce7-4ccb-a1e1-a1f9614226f1" />
<br>
---

### Step 6: Reporting
- Click **Generate Report** from the toolbar.  
- Choose report type: HTML, CSV, Excel, etc.  
- Select which parts of analysis to include.
<br>
<img width="500" alt="image" src="https://github.com/user-attachments/assets/db37d30b-7505-4e73-ba31-7ac9495ff0f3" />
<br>
- Export findings (files or artifacts).  
- Review and finalize the report.  

---

### Step 7: Case Closure
- Close the case in Autopsy.  
- Archive data & reports as per organizational policy.
<br>
<img width="500" alt="image" src="https://github.com/user-attachments/assets/efddac57-e6d5-446f-9a71-fcf6cee05561" />
<br>

---

# Rubrics
| Criteria | Mark Allotted | Mark Awarded |
|---|:---:|:---:|
| 1. GitHub Activity & Submission Regularity | 3 | |
| 2. Application of Forensic Tools & Practical Execution | 3 | |
| 3. Documentation & Reporting | 2 | |
| 4. Engagement, Problem-Solving & Team Collaboration | 2 | |
| Total | 10 | |

---

## Result
Successfully created a case in Autopsy, imported a forensic disk image, analyzed artifacts, and generated a forensic report.  

---


