# Ex. No 6: Use Sleuth Kit to Analyze Digital Evidence

---

## 🎯 Aim
To analyze a disk image and recover digital evidence using **The Sleuth Kit (TSK)** command-line tools.

---

## 📌 Description
**The Sleuth Kit (TSK)** is a collection of open-source command-line tools that allow forensic investigators to analyze disk images, recover deleted files, and extract metadata.  
It supports file system analysis, partition inspection, and timeline creation — essential steps in any digital investigation.

📂 **Drive Link for Tools & Evidence Files**  
- [Digital Forensics Tools & Evidence Files](https://drive.google.com/drive/u/1/folders/1ilSFY7Tqn2L7AjQGhq8yJ8kixc_xTU-v)  
- Files:
  - `4Dell Latitude CPi.E01`
  - `4Dell Latitude CPi.E02`


---

## 📝 Steps

### Step 1: Installation
- Download and install **The Sleuth Kit (TSK)** for Windows from its [official website](https://www.sleuthkit.org/sleuthkit/download.php).  
- Follow on-screen installation instructions.

---

<img width="1919" height="1079" alt="1" src="https://github.com/user-attachments/assets/cb8d8d85-346e-42a0-81a8-0df9eab4f6eb" />


---

### Step 2: Acquire the Disk Image
- Create or obtain a forensic disk image using tools like **FTK Imager** or **dd**.  
- Supported formats: `.dd`, `.raw`, `.img`, `.E01`  
- Example evidence files:  
  - `4Dell Latitude CPi.E01`  
  - `4Dell Latitude CPi.E02`


---

### Step 3: (Optional) Mount the Disk Image
- Use **OSFMount** to mount the `.E01` or `.dd` image as a virtual drive.  
- This helps in manually browsing the contents if needed.


---

### Step 4: Analyze the File System

#### 🔹 Navigate to Sleuth Kit:
Run:
```bash
cd C:\Users\M J B NAIDU\OneDrive\Desktop\DF Lab Exp\Exp_6\sleuthkit-4.14.0-win32\bin
```

<img width="1479" height="771" alt="2" src="https://github.com/user-attachments/assets/2dc048db-6101-4e55-994f-47b49da9c97e" />

---

#### 🔹 Identify File System Type:
Run:
```bash
fsstat.exe -o 63 "C:\Users\M J B NAIDU\OneDrive\Desktop\DF Lab Exp\Exp_6\4Dell Latitude CPi.E01"
```
This command gives details about the file system type, layout, and structure.

<img width="1488" height="922" alt="3" src="https://github.com/user-attachments/assets/206f9a59-733d-495f-a8f9-0062ec3f9506" />


---

#### 🔹 List Partitions:
Run:
```bash
mmls.exe "C:\Users\M J B NAIDU\OneDrive\Desktop\DF Lab Exp\Exp_6\4Dell Latitude CPi.E01"
```
This lists all partitions present in the disk image.

<img width="1482" height="759" alt="4" src="https://github.com/user-attachments/assets/c46c0fcb-3b0b-4a4d-a349-fd88ceb913f6" />


---

#### 🔹 List Files and Directories
Run:
```bash
fls.exe -r -o 63 "C:\Users\M J B NAIDU\OneDrive\Desktop\DF Lab Exp\Exp_6\4Dell Latitude CPi.E01"
```
This recursively lists all files and directories, including deleted ones.

<img width="1237" height="920" alt="5" src="https://github.com/user-attachments/assets/db85b4f2-b476-44d1-8c89-c6e5695e90ed" />


---

#### 🔹 Recover Deleted Files
Run:
```bash
icat.exe -o 63 "C:\Users\M J B NAIDU\OneDrive\Desktop\DF Lab Exp\Exp_6\4Dell Latitude CPi.E01" 11366 > C:\Users\M J B NAIDU\OneDrive\Desktop\DF Lab Exp\Exp_6\recovered_file.jpg
```
<img width="1289" height="667" alt="6" src="https://github.com/user-attachments/assets/945bc934-3a5c-4dd2-8293-07e5d86c13de" />


---

### Step 5: Analyze Metadata
Use the `istat` command to extract metadata of a specific file:
```bash
istat.exe -o 63  "C:\Users\M J B NAIDU\OneDrive\Desktop\DF Lab Exp\Exp_6\4Dell Latitude CPi.E01" 11366 > C:\Users\M J B NAIDU\OneDrive\Desktop\DF Lab Exp\Exp_6\recovered_file.txt
```
This provides information such as:
- File creation, modification, and access timestamps  
- File size and allocation status  

![7](https://github.com/user-attachments/assets/2b810d1c-c2b0-46de-9fa7-724d7888bc7b)



---

### Step 6: Timeline Analysis (Optional)
Generate a chronological timeline of file system activity.

1. Create a **body file**:
   ```bash
   fls.exe -m / -r -o 63 "C:\Users\M J B NAIDU\OneDrive\Desktop\DF Lab Exp\Exp_6\4Dell Latitude CPi.E01" > C:\Users\M J B NAIDU\OneDrive\Desktop\DF Lab Exp\Exp_6\body.txt
   ```
   ![8](https://github.com/user-attachments/assets/669c3048-045d-4c3f-98e0-bd9955589710)

2. Generate the **timeline**:
   ```bash
   mactime -b body.txt > timeline.txt
   ```

This file lists the **MAC (Modified, Accessed, Changed)** timestamps of all files.


---

### Step 7: Reporting
1. Collect all analysis outputs:
   - `filesystem_info.txt`
   - `partitions.txt`
   - `file_list.txt`
   - `metadata_info.txt`
   - `timeline.txt` (if created)

2. Review and summarize findings such as:
   - File system type and structure  
   - Deleted or recovered files  
   - File metadata insights  
   - Activity timeline (if available)


---

### Step 8: Finalize and Store Evidence
- Archive all reports and analysis files securely.  
- Maintain the **chain of custody** to ensure evidence integrity.  
- Store archives in a **secure and access-controlled** environment.


---

## ✅ Result
Successfully analyzed the given disk image using **The Sleuth Kit (TSK)**.  
Extracted file system information, recovered deleted files, analyzed metadata, and generated a forensic timeline report.

---

## 📌 Notes
- Always analyze **forensic copies**, not the original evidence media.  
- Maintain documentation for every step in the investigation.  
- Ensure that all extracted evidence and reports are securely stored.  
- The Sleuth Kit provides powerful tools like:
  - `fsstat` — File system details  
  - `mmls` — Partition listing  
  - `fls` — File and directory listing  
  - `icat` — File recovery  
  - `istat` — Metadata extraction  
  - `mactime` — Timeline generation  

---

## 📚 References
- [The Sleuth Kit Official Website](https://www.sleuthkit.org/)  
- [Autopsy Official Documentation](https://www.autopsy.com/)  
- Digital Forensics and Incident Response (DFIR) Tutorials  
- Carrier, B. (2018). *File System Forensic Analysis.*

---
