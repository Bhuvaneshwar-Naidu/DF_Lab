# Ex No - 06  
## Use Sleuth Kit to Analyze Digital Evidence

---

### **Aim**
To use the Sleuth Kit (TSK) to analyze digital evidence from a disk image and recover forensic data.

---

### **Description**
The Sleuth Kit (TSK) is a collection of command-line tools used for digital forensics. It enables investigators to analyze disk images, examine file systems, recover deleted files, and extract metadata.  
This experiment demonstrates how to use Sleuth Kit on a Windows machine for evidence analysis.

---

### **Step-by-Step Procedure**

#### **Step 1: Install Sleuth Kit**
1. Download Sleuth Kit from the official website or from:  
   [Google Drive Link](https://drive.google.com/drive/u/1/folders/1ilSFY7Tqn2L7AjQGhq8yJ8kixc_xTU-v)
2. Run the installer and follow the on-screen instructions to install it on your Windows system.

---

#### **Step 2: Acquire the Disk Image**
1. Obtain or create a disk image of the evidence (hard drive, memory card, etc.).
2. Use tools like **FTK Imager** or **dd** to create a bit-by-bit image.
3. Ensure the file format is supported by Sleuth Kit (`.dd`, `.raw`, `.img`, `.E01`).
4. Download the sample evidence files:
   - `4Dell Latitude CPi.E01`
   - `4Dell Latitude CPi.E02`

---

#### **Step 3: Mount the Disk Image (Optional)**
1. Use **OSFMount** or a similar tool to mount the disk image as a virtual drive.
2. This makes it easier to explore the file system manually (optional step).

---

#### **Step 4: Analyze the File System**
1. Open **Command Prompt** and navigate to the Sleuth Kit installation directory.
2. **Identify File System Type:**
   ```bash
   fsstat [image file] > filesystem_info.txt
