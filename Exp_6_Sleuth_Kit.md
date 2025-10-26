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
- Files: `4Dell Latitude CPi.E01`
-         `4Dell Latitude CPi.E02`

---

## 📝 Steps

### Step 1: Installation
- Download and install **The Sleuth Kit (TSK)** for Windows from its [official website](https://www.sleuthkit.org/).  
- Follow on-screen installation instructions.

📸 *Screenshot 1: Sleuth Kit installation window or command prompt showing version*  
`(Insert Screenshot Here)`

---

### Step 2: Acquire the Disk Image
- Create or obtain a forensic disk image using tools like **FTK Imager** or **dd**.  
- Supported formats: `.dd`, `.raw`, `.img`, `.E01`  
- Example evidence files:  
  - `4Dell Latitude CPi.E01`  
  - `4Dell Latitude CPi.E02`

📸 *Screenshot 2: Evidence image files visible in directory*  
`(Insert Screenshot Here)`

---

### Step 3: (Optional) Mount the Disk Image
- Use **OSFMount** to mount the `.E01` or `.dd` image as a virtual drive.  
- This helps in manually browsing the contents if needed.

📸 *Screenshot 3: OSFMount showing mounted image*  
`(Insert Screenshot Here)`

---

### Step 4: Analyze the File System

#### 🔹 Identify File System Type
Run:
```bash
fsstat [image file] > filesystem_info.txt
```
This command gives details about the file system type, layout, and structure.

📸 *Screenshot 4: Output of fsstat command in Command Prompt*  
`(Insert Screenshot Here)`

---

#### 🔹 List Partitions
Run:
```bash
mmls [image file] > partitions.txt
```
This lists all partitions present in the disk image.

📸 *Screenshot 5: mmls output showing partitions*  
`(Insert Screenshot Here)`

---

#### 🔹 List Files and Directories
Run:
```bash
fls -r [image file] > file_list.txt
```
This recursively lists all files and directories, including deleted ones.

📸 *Screenshot 6: fls command output showing file and inode list*  
`(Insert Screenshot Here)`

---

#### 🔹 Recover Deleted Files
Run:
```bash
icat [image file] [inode number] > recovered_file.txt
```
Replace `[inode number]` with the value obtained from the `fls` command output.

📸 *Screenshot 7: icat command recovering deleted file*  
`(Insert Screenshot Here)`

---

### Step 5: Analyze Metadata
Use the `istat` command to extract metadata of a specific file:
```bash
istat [image file] [inode number] > metadata_info.txt
```
This provides information such as:
- File creation, modification, and access timestamps  
- File size and allocation status  

📸 *Screenshot 8: istat command output showing file metadata*  
`(Insert Screenshot Here)`

---

### Step 6: Timeline Analysis (Optional)
Generate a chronological timeline of file system activity.

1. Create a **body file**:
   ```bash
   fls -m / -r [image file] > body.txt
   ```
2. Generate the **timeline**:
   ```bash
   mactime -b body.txt > timeline.txt
   ```

This file lists the **MAC (Modified, Accessed, Changed)** timestamps of all files.

📸 *Screenshot 9: timeline.txt showing chronological events*  
`(Insert Screenshot Here)`

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

📸 *Screenshot 10: Folder view showing all generated result files*  
`(Insert Screenshot Here)`

---

### Step 8: Finalize and Store Evidence
- Archive all reports and analysis files securely.  
- Maintain the **chain of custody** to ensure evidence integrity.  
- Store archives in a **secure and access-controlled** environment.

📸 *Screenshot 11: Archived evidence folder (ZIP/RAR) showing final stored data*  
`(Insert Screenshot Here)`

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
