# **Ex.No.8: Use StegExpose to Detect Hidden Data in Images**

---

## 🎯 **Aim**
To detect the presence of hidden data within digital images using **StegExpose**, a steganalysis tool that evaluates image statistics to identify steganographic content.

---

## 🧩 **Description**
**Steganography** is a technique used to hide secret information within a normal file, such as an image, audio, or video, without changing its visible or audible appearance. It conceals the existence of the message rather than its content, making communication more secure. The most common method is using the Least Significant Bit (LSB) technique to embed data within digital media.

## ⚙️ **Step-by-Step Procedure**

### **Step1️: Download and Set Up for Steganography**
1. Visit the **StegExpose GitHub page** and download the `.jar` file.  
2. Ensure **Java** is installed on your system. If not, download it from [Oracle’s official website](https://www.oracle.com/java/technologies/javase-downloads.html).  
3. Place the `StegExpose.jar` file in your working directory (e.g., `C:\DF\StegExpose\`).
<img width="971" height="650" alt="1" src="https://github.com/user-attachments/assets/5150500a-ebe2-42b8-8a06-f9580a65b74d" />

---

### **Step2️: Select Images for Analysis**
- Collect images you suspect might contain hidden data.  
- Supported formats include `.png`, `.jpg`, and `.bmp`.
<img width="957" height="864" alt="2" src="https://github.com/user-attachments/assets/64f2954d-3eae-4ba0-b49b-663bbfcf6194" />

---

### **Step3️: Compare and Save the Stegno Image**
1. Compare the difference between the normal and the stegnoimage.
2. Right click the image and click on save image.
3. Name the file as **Stegno image** and click on save.
<img width="933" height="647" alt="3" src="https://github.com/user-attachments/assets/0ba724b0-76b2-4117-a43f-f86f8c1ee1d5" />

---

### **4️⃣ Run Decode on a Stegno Image**
1. Select the image you want decode.
2. Click on decode.
<img width="957" height="759" alt="4" src="https://github.com/user-attachments/assets/23f2db38-1148-410e-b5ee-d771ca214125" />

---

### **5️⃣ Analyze the Output**
<img width="942" height="617" alt="5" src="https://github.com/user-attachments/assets/29d581c0-7ba4-4f87-9c74-f360d859419a" />



```

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
