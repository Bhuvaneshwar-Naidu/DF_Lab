# Ex.No.1   Evidence Acquisition with FTK Imager

## 🎯 Objective
To acquire **volatile memory (RAM)** and **non-volatile memory (disk image)** from a target system using **AccessData FTK Imager**, while preserving integrity through hashing and proper documentation.

---

## 🔹 Acquiring Volatile Memory (RAM)

### Step 1: Launch FTK Imager as Administrator
- Right-click on **FTK Imager** and select **Run as Administrator**.  
- This ensures the tool has sufficient privileges to access system memory.

<br>

<img width="1575" height="763" alt="image" src="https://github.com/user-attachments/assets/739f9871-3976-41c3-be50-b8a8da805b63" />

<br>

---

### Step 2: Open Capture Memory Utility
- In the **Menu Bar**, click **File → Capture Memory...**  

<br>

<img width="1919" height="1096" alt="image" src="https://github.com/user-attachments/assets/8b6eead1-d327-43b7-be00-1b081822ebe5" />

<br>

---

### Step 3: Configure Capture Options
In the pop-up dialog:  

- **Destination Path** → Choose an **external drive** (not the system drive).  
- **Destination Filename** → Default is `memdump.mem` (rename if required).  
- **Include Pagefile.sys (Optional)** → Captures virtual memory stored on disk.  
- **Create AD1 File (Optional)** → Wraps output into an AccessData container.  

> 💡 *Tip:* Including `pagefile.sys` can reveal hidden processes and artifacts.

<br>

<img width="1918" height="1098" alt="image" src="https://github.com/user-attachments/assets/37f79f46-b802-4028-a10e-659874ebc6e2" />

---

### Step 4: Begin Capture
- Click **Capture Memory** to start.  
- A progress bar shows the status.

<br>

<img width="1914" height="868" alt="image" src="https://github.com/user-attachments/assets/1194796f-767d-4e59-8e3a-5962823bdda1" />

---

### Step 5: Completion
- The `.mem` file will be created in the destination folder.  
- Capture time depends on installed RAM size.  

---

## 🔹 Acquiring Non-Volatile Memory (Disk Image)

### Step 1: Start Disk Imaging
- In FTK Imager, go to **File → Create Disk Image...**

<br>

<img width="1918" height="1066" alt="image" src="https://github.com/user-attachments/assets/479850a5-c2fb-4695-b830-2ab9dc3cc63d" />

---

### Step 2: Select Source Type
Choose based on requirement:  
- **Physical Drive** → Entire disk (preferred).  
- **Logical Drive** → Single partition (e.g., C:).  
- **Image File** → Re-image an existing file.  
- **Folder / CD/DVD** → Acquire folder or removable media.

> ✅ *Forensic best practice:* Always select **Physical Drive** with a **write blocker**.

<br>

<img width="591" height="433" alt="image" src="https://github.com/user-attachments/assets/057d577e-5327-44e8-93b5-da3b5fca1fed" />

---

### Step 3: Select Drive
- Pick the drive from the list.  
- Confirm and click **Finish**.

<br>

<img width="583" height="428" alt="image" src="https://github.com/user-attachments/assets/7174ba85-f638-4ca5-b299-65dc9841d3ea" />

---

### Step 4: Configure Destination & Format
- Click **Add...** to define image format and storage path.  
- **Image Type:**  
  - `E01 (EnCase)` → Recommended (metadata + compression).  
  - `RAW (dd)` → Bit-for-bit copy.  
- Enter **Case Info**: Examiner, Case No., Notes.  
- Set **Destination Folder** (different from source).  
- **Fragment Size:** Set `0` for a single file.

<br>

<img width="505" height="405" alt="image" src="https://github.com/user-attachments/assets/e5d806b5-edda-4f57-a60b-e4c58b8fd343" />

---

### Step 5: Imaging Process
- Check **Verify images after creation** to generate hash values.  
- Click **Start** to begin acquisition.  

<br>

<p align="center">
  <img width="300" alt="progress1" src="https://github.com/user-attachments/assets/739045f1-11bc-474a-9343-2e9aa19ec376" />
  <img width="300" alt="progress2" src="https://github.com/user-attachments/assets/7bef2114-0017-4a7b-9e19-0f356c3e3236" />
</p>

---

### Step 6: Verify Integrity
- On completion, FTK Imager displays **MD5/SHA1** hashes.  
- If hashes match, the image is valid and unaltered.  

---

## 📌 Notes
- Always use a **hardware write-blocker** when acquiring from suspect drives.  
- Document **case details, examiner info, and timestamps**.  
- Perform **hash verification** to maintain admissibility in court.  
- Use **fragmentation** only if destination media has file size limits.  

---

## 📚 References
- [FTK Imager Official Download](https://accessdata.com/product-download/ftk-imager-version-4-5)  
- AccessData Documentation  
- Forensic Best Practices Guidelines  

---
