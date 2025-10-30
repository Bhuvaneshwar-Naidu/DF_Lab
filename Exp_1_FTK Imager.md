# Ex.No.1   Evidence Acquisition with FTK Imager

## Aim
To acquire **volatile memory (RAM)** and **non-volatile memory (disk image)** from a target system using **AccessData FTK Imager**, while preserving integrity through hashing and proper documentation.

---
##  Acquiring Volatile Memory (RAM)
### Step 1: Launch FTK Imager as Administrator
- Right-click on **FTK Imager** and select **Run as Administrator**.  
- This ensures the tool has sufficient privileges to access system memory.

<br>
<img width="400" alt="image" src="https://github.com/user-attachments/assets/739f9871-3976-41c3-be50-b8a8da805b63" />
<br>

---

### Step 2: Open Capture Memory Utility
- Below the **Menu Bar**, click **Capture Memory...**  

<br>

<img width="500" alt="FTK1" src="https://github.com/user-attachments/assets/9b939af8-4e18-447d-8fa1-2047300f84bb" />


<br>

---

### Step 3: Configure Capture Options
In the pop-up dialog:  

- **Destination Path** → Choose an **external drive** (not the system drive).  
- **Destination Filename** → Default is `memdump.mem` (rename if required).  
- **Include Pagefile.sys (Optional)** → Captures virtual memory stored on disk.  
- **Create AD1 File (Optional)** → Wraps output into an AccessData container.  

>  *Tip:* Including `pagefile.sys` can reveal hidden processes and artifacts.

<br>

<img width="500" alt="Screenshot (8)" src="https://github.com/user-attachments/assets/b07dbfed-d070-4037-ad52-03879e1e3c05" />


---

### Step 4: Begin Capture
- Click **Capture Memory** to start.  
- A progress bar shows the status.

<br>

<img width="500" alt="Screenshot (9)" src="https://github.com/user-attachments/assets/1df681a5-3fdb-4c44-a4f9-7eb830c0524d" />


---

### Step 5: Completion
- The `.mem` file will be created in the destination folder.  
- Capture time depends on installed RAM size.

<br>

<img width="500" alt="Screenshot (10)" src="https://github.com/user-attachments/assets/df1137b0-dcea-4dda-b6aa-cf91620086a3" />



---

##  Acquiring Non-Volatile Memory (Disk Image)

### Step 1: Start Disk Imaging
- In FTK Imager, go to **File → Create Disk Image...**

<br>

<img width="500" alt="Screenshot (11)" src="https://github.com/user-attachments/assets/7f0d6320-a523-49ff-bc03-f6ed463dd4da" />


---

### Step 2: Select Source Type
Choose based on requirement:  
- **Physical Drive** → Entire disk (preferred).  
- **Logical Drive** → Single partition (e.g., C:).  
- **Image File** → Re-image an existing file.  
- **Folder / CD/DVD** → Acquire folder or removable media.

>  *Forensic best practice:* Always select **Physical Drive** with a **write blocker**.

<br>

<img width="400" alt="Screenshot (12)" src="https://github.com/user-attachments/assets/93a58f63-3ef5-4f38-a2c5-5d14d5b65f81" />


---

### Step 3: Select Drive
- Pick the drive from the list.  
- Confirm and click **Finish**.

<br>

<img width="500" alt="Screenshot (13)" src="https://github.com/user-attachments/assets/af7f2a1a-5d50-4513-a18e-9da3f6314bc3" />


---

### Step 4: Configure Destination & Format  
- Click **Add...** to define image format and storage path.
<img width="500" alt="Screenshot (14)" src="https://github.com/user-attachments/assets/3b8623f6-45d9-463e-a7c4-f9ac46811dae" />  
<br><br>

- **Image Type:**  
  - `E01 (EnCase)` → Recommended (metadata + compression).  
  - `RAW (dd)` → Bit-for-bit copy.
<img width="500" alt="Screenshot (15)" src="https://github.com/user-attachments/assets/89f275dd-f350-4e76-8a99-b5e5188e9594" />  
<br><br>

- Enter **Case Info**: Examiner, Case No., Notes.
<img width="500" alt="Screenshot (19)" src="https://github.com/user-attachments/assets/8c8cfb43-1ec4-4475-b9d8-6ed614cb8d41" />  
<br><br>

- Set **Destination Folder** (different from source).  
- **Fragment Size:** Set `0` for a single file.
<img width="500" alt="Screenshot (20)" src="https://github.com/user-attachments/assets/275c3c07-e4a3-4ba0-b495-d7cbf56d1973" />
<br><br>

---

### Step 5: Imaging Process
- Check **Verify images after creation** to generate hash values.  
- Click **Start** to begin acquisition.  

<br>

<p align="center">
  <img width="500" alt="Screenshot (21)" src="https://github.com/user-attachments/assets/6f9ccad3-94b2-4ca0-97eb-795580cf948e" />  
  
<img width="500" alt="Screenshot (22)" src="https://github.com/user-attachments/assets/3bcf40e5-3f03-4063-a067-f8bc7fc64624" />

</p>

---

### Step 6: Verify Integrity
- On completion, FTK Imager displays **MD5/SHA1** hashes.  
- If hashes match, the image is valid and unaltered.  

<br>

<p align="center">
  <img width="500" alt="Screenshot (23)" src="https://github.com/user-attachments/assets/2d5fabc2-5350-4bd7-95e9-bddb7f059a13" />  
  
<img width="500" alt="Screenshot (25)" src="https://github.com/user-attachments/assets/d9e45263-634d-47ff-8d09-9356be888e45" />


</p>

---
## Rubrics
| Criteria | Mark Allotted | Mark Awarded |
|---|:---:|:---:|
| 1. GitHub Activity & Submission Regularity | 3 | |
| 2. Application of Forensic Tools & Practical Execution | 3 | |
| 3. Documentation & Reporting | 2 | |
| 4. Engagement, Problem-Solving & Team Collaboration | 2 | |
| *Total* | *10* | |

--- 

##  **Result**
Successfully acquired the **RAM dump (.mem)** and **disk image (.E01)** of the target system using **FTK Imager**.  
The **MD5/SHA1 hash values** of the acquired images were verified, confirming that the evidence was collected without alteration and is **forensically sound**.






