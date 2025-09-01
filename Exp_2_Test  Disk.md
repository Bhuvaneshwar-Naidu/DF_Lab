# Ex.No.2   Recover Deleted or Damaged Files using TestDisk

## 🎯 Aim
To use **TestDisk** step-by-step to recover a missing partition, repair a corrupted partition, and restore access to lost files.

---

## 🔹 Step 1: Log Creation & Disk Detection

### Log Creation
- When TestDisk starts, Select the [Create] option to generate a log file of the recovery session. This is helpful for future reference or troubleshooting.  
<img width="1103" height="639" alt="Test_Disk1" src="https://github.com/user-attachments/assets/4e0689a7-16c4-41cd-b2bc-65dfa7f9552e" />

<br>
<br>

### Disk Detection
- All hard drives will be listed with their correct sizes.  

➡️ Use the **Up/Down arrow keys** to select the target disk.  
> 💡 If available, prefer `/dev/rdisk*` (raw device) over `/dev/disk*` for faster performance
- Select [Proceed] to move to the next step.
<img width="1103" height="639" alt="Test_Disk2" src="https://github.com/user-attachments/assets/1349cc44-c2ac-4bcf-89be-7b81f45edf04" />

---

## 🔹 Step 2: Partition Table Type Selection
- TestDisk auto-detects the partition table type.  
- Usually, the **default value is correct**.  
- Press **Enter** to proceed.
<img width="1103" height="639" alt="Test_Disk3" src="https://github.com/user-attachments/assets/bd873104-ebef-451b-b61a-480f3701b78a" />

---

## 🔹 Step 3: Analyse Partition Structure
- Select **Analyse** from the menu to view the current partition structure.  
- Missing or corrupted partitions will be shown here.  

> Example issues:  
- A partition listed twice → indicates corruption.  
- "Invalid NTFS boot" → damaged NTFS boot sector.  
- Missing logical partition(s).

- Press **Enter** to proceed to **Quick Search**.
<img width="1103" height="639" alt="Test_Disk4" src="https://github.com/user-attachments/assets/44f86f9c-aa43-4917-8e58-8312fc254bca" />

---

## 🔹 Step 4: Quick Search for Partitions
- TestDisk performs a **Quick Search** and lists found partitions in real-time.  
- Highlight the missing partition and press **p** to list its files.  

> 🔎 Files in **red** are deleted entries. Use **q** to go back.

- If all looks correct, press **Enter** to continue.
<img width="1103" height="639" alt="Test_Disk5" src="https://github.com/user-attachments/assets/118ba03c-9d83-4e80-94be-99531544994a" />

---

## 🔹 Step 5: Save Partition Table / Deeper Search
- If not all partitions are visible, select **Deeper Search**.  
- This scans for backup boot sectors (FAT32, NTFS, ext2/ext3) cylinder by cylinder.
- This process can take a long time, as it scans the entire drive, block by block, to find remnants of partition structures.
- Again, use p to preview files and confirm if a found partition is the one you are looking for.  
<img width="1103" height="639" alt="Test_Disk6" src="https://github.com/user-attachments/assets/2de94f91-37ba-4a6d-a756-408c95057b03" />
<br>
<br>

➡️ After the deeper scan:
- Partitions found using backup boot sectors are listed.  
- Overlapping or corrupted entries will appear as **D (Deleted)**.  

- Highlight the correct partition and press **p** to verify its files.  
- Use **Left/Right arrow keys** to change partition status:
  - `P` → Primary  
  - `*` → Bootable  
  - `L` → Logical  
  - `D` → Deleted  
<img width="1103" height="639" alt="Test_Disk7" src="https://github.com/user-attachments/assets/bf1d4980-809f-455c-a56d-e643eb0ad70d" />

---

## 🔹 Step 6: Partition Table Recovery
- Once correct partitions are marked:  
  - Confirm with **Write** → press **Enter**, then `y`, then **OK**.  
- TestDisk updates the partition table automatically.
<img width="1103" height="639" alt="Test_Disk8" src="https://github.com/user-attachments/assets/11076c0f-eaef-4658-a68d-968276062251" />

<br>

<img width="1103" height="639" alt="Test_Disk9" src="https://github.com/user-attachments/assets/f04b6be8-5279-444e-abf3-2b012a18d526" />

---

## 🔹 Step 7: NTFS Boot Sector Recovery
- If NTFS boot sector is damaged:  
  - Select **Backup BS** to copy the backup boot sector over the bad one.  
  - Confirm with **y** → then **OK**.  

✅ Now the boot sector and backup are identical, meaning recovery succeeded.

---

## 🔹 Step 8: Restart System
- After successful recovery, TestDisk prompts you to **reboot the computer**.  
- Restart and check if your partitions and files are accessible again.
<img width="1103" height="639" alt="Test_Disk10" src="https://github.com/user-attachments/assets/36bf3e34-90b8-4c84-a1b5-0f4e4514565e" />

---

## 📌 Notes
- Always work on a **copy/clone** of the disk to avoid further damage.  
- **Quick Search** is fast but may miss deep corruption → always confirm with **Deeper Search** if needed.  
- Be careful when marking overlapping partitions; only the correct one should be set to recoverable.  

---

## 📚 References
- [TestDisk Official Documentation](https://www.cgsecurity.org/wiki/TestDisk_Step_By_Step)  
- TestDisk Menu Items Guide  

---
