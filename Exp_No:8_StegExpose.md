# **Ex.No.8: Use StegExpose to Detect Hidden Data in Images**

---

## 🎯 **Aim**
To detect the presence of hidden data within digital images using **StegExpose**, a steganalysis tool that evaluates image statistics to identify steganographic content.

---

## 🧩 **Description**
**StegExpose** is an open-source Java-based tool designed for detecting **steganography** (hidden data) in images.  
It performs **statistical analysis** on image properties to estimate the probability that data has been embedded within an image file.

The tool supports common formats such as **.png**, **.jpg**, and **.bmp**, and produces a “suspect score” for each analyzed image.

---

## 🧰 **Prerequisites**
- **Java Runtime Environment (JRE):** Required to run StegExpose.  
- **StegExpose Tool:** Download from the [official GitHub repository](https://github.com/b3dk7/StegExpose).

---

## ⚙️ **Step-by-Step Procedure**

### **1️⃣ Download and Set Up StegExpose**
1. Visit the **StegExpose GitHub page** and download the `.jar` file.  
2. Ensure **Java** is installed on your system. If not, download it from [Oracle’s official website](https://www.oracle.com/java/technologies/javase-downloads.html).  
3. Place the `StegExpose.jar` file in your working directory (e.g., `C:\DF\StegExpose\`).

---

### **2️⃣ Select Images for Analysis**
- Collect images you suspect might contain hidden data.  
- Supported formats include `.png`, `.jpg`, and `.bmp`.

---

### **3️⃣ Open Command Line or Terminal**
1. Navigate to the folder containing `StegExpose.jar`.  
2. Open **Command Prompt (Windows)** or **Terminal (Linux/macOS)**.

---

### **4️⃣ Run StegExpose on a Single Image**
Use the following command to analyze an image:

```bash
java -jar StegExpose.jar <image_file_path>
```

**Example:**
```bash
java -jar StegExpose.jar test_image.png
```

Replace `<image_file_path>` with the full path to your image file.

---

### **5️⃣ Analyze the Output**
StegExpose generates a **suspect score** between **0 and 1** indicating the likelihood of hidden data.

| Score Range | Interpretation |
|--------------|----------------|
| < 0.2 | Clean (No hidden data) |
| 0.2 - 0.3 | Possibly hidden data |
| > 0.3 | Likely contains steganography |

**Example Output:**
```bash
Analyzing suspect_image.png...
Result: 0.4
Steganography likely present
```

---

### **6️⃣ Perform Batch Analysis (Multiple Images)**
To analyze all images in a folder:

```bash
java -jar StegExpose.jar <folder_path>
```

Replace `<folder_path>` with the directory containing multiple images.

---

### **7️⃣ Advanced Options (Optional)**
To view additional parameters and configuration options, run:

```bash
java -jar StegExpose.jar --help
```

This command lists available arguments such as detection **sensitivity**, **verbosity**, and **output report settings**.

---

### **8️⃣ Review and Document the Results**
For each image analyzed, review the suspect scores.  
Higher scores indicate a stronger likelihood of hidden steganographic content.

---

## ✅ **Result**
Successfully used **StegExpose** to perform steganalysis on images, identified potential hidden data through suspect scores, and interpreted the likelihood of steganography based on the tool’s statistical output.

---

## 🧾 **Notes (Optional)**
- Ensure images are unaltered before analysis for accurate results.  
- Use a consistent file format during testing to avoid false positives.  
- Results should be verified with additional forensic tools if necessary.

---

## 📚 **References**
- [StegExpose GitHub Repository](https://github.com/b3dk7/StegExpose)  
- [Oracle Java Downloads](https://www.oracle.com/java/technologies/javase-downloads.html)  
- [Introduction to Steganalysis - Research Paper](https://ieeexplore.ieee.org/document/6714473)

---
