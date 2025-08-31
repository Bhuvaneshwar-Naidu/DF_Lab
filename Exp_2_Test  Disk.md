# Ex.No.2   Recover Deleted or Damaged Files using TestDisk

## 🎯 Aim
To use **TestDisk** step-by-step to recover a missing partition, repair a corrupted partition, and restore access to lost files.

---

## 🔹 Step 1: Log Creation & Disk Detection
- When TestDisk starts, it creates a **log file** automatically.  
- All hard drives will be listed with their correct sizes.  

➡️ Use the **Up/Down arrow keys** to select the target disk.  
> 💡 If available, prefer `/dev/rdisk*` (raw device) over `/dev/disk*` for faster performance.

---

## 🔹 Step 2: Partition Table Type Selection
- TestDisk auto-detects the partition table type.  
- Usually, the **default value is correct**.  
- Press **Enter** to proceed.

---

## 🔹 Step 3: Analyse Partition Structure
- Select **Analyse** from the menu to view the current partition structure.  
- Missing or corrupted partitions will be shown here.  

> Example issues:  
- A partition listed twice → indicates corruption.  
- "Invalid NTFS boot" → damaged NTFS boot sector.  
- Missing logical partition(s).

- Press **Enter** to proceed to **Quick Search**.

---

## 🔹 Step 4: Quick Search for Partitions
- TestDisk performs a **Quick Search** and lists found partitions in real-time.  
- Highlight the missing partition and press **p** to list its files.  

> 🔎 Files in **red** are deleted entries. Use **q** to go back.

- If all looks correct, press **Enter** to continue.

---

## 🔹 Step 5: Save Partition Table / Deeper Search
- If not all partitions are visible, select **Deeper Search**.  
- This scans for backup boot sectors (FAT32, NTFS, ext2/ext3) cylinder by cylinder.  

➡️ After the deeper scan:
- Partitions found using backup boot sectors are listed.  
- Overlapping or corrupted entries will appear as **D (Deleted)**.  

- Highlight the correct partition and press **p** to verify its files.  
- Use **Left/Right arrow keys** to change partition status:
  - `P` → Primary  
  - `*` → Bootable  
  - `L` → Logical  
  - `D` → Deleted  

---

## 🔹 Step 6: Partition Table Recovery
- Once correct partitions are marked:  
  - Confirm with **Write** → press **Enter**, then `y`, then **OK**.  
- TestDisk updates the partition table automatically.

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
