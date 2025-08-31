# Ex. No 4: Analyze Email Headers and Detect Email Spoofing using MHA (Mail Header Analyzer)

---

## 🎯 Aim
To analyze an email header and detect possible **email spoofing** using the **Mail Header Analyzer (MHA)** tool.

---

## 📌 Description
Email headers contain important metadata about an email’s journey from the sender to the recipient. By analyzing these headers, we can identify anomalies such as forged sender details, unauthorized IPs, or failed authentication checks (SPF, DKIM, DMARC), which are common signs of **email spoofing**.

---

## 📝 Steps

### Step 1: Access the Email Header
- **Gmail**: Open the email → Click the three dots (More) → Select **Show Original**  
- **Outlook**: Open the email → Click on **File → Properties** → Copy from **Internet headers**  
- **Yahoo**: Open the email → Click the three dots (More) → Select **View Raw Message**

---


### Step 2: Copy the Email Header
- Copy the entire header text (contains details like `Received`, `Message-ID`, `SPF`, `DKIM`, etc.)
- Save it into a text file or keep it ready to paste into an analysis tool.

---

### Step 3: Use Mail Header Analyzer (MHA)
1. Open [Google Admin Toolbox MHA](https://toolbox.googleapps.com/apps/messageheader/)  
2. Paste the copied email header into the text box.  
3. Click **Analyze the Header**.  

---

### Step 4: Interpret the Results
- **Received Chain** → Shows the exact path (servers & timestamps) the email took.  
- **Delay Analysis** → Highlights unusual delays that might indicate suspicious routing.  
- **SPF/DKIM/DMARC** → Shows authentication results.  
   - ✅ **Pass** → Email is genuine.  
   - ❌ **Fail** → Possible spoofing attempt.  
- **Message-ID** → Should match the sender’s domain; mismatch may indicate forgery.  

---

## 🖼️ Example Output (MHA Tool)

- **Source IP**: `192.0.2.1` (verified via WHOIS → belongs to `mail.example.com`)  
- **SPF**: ❌ Fail (IP not authorized)  
- **DKIM**: ❌ Fail (message integrity could not be verified)  
- **DMARC**: ❌ Fail (policy not aligned)  
- **Conclusion**: Email is very likely **spoofed**.  

---

## ✅ Result
Successfully analyzed the email header using **MHA (Mail Header Analyzer)**.  
Detected **spoofing indicators** by examining **SPF/DKIM/DMARC failures** and mismatched header fields.  

---

## 📌 Notes
- Always verify suspicious emails before clicking links or downloading attachments.  
- Spoofed emails are often used for **phishing attacks**.  
- This experiment is for **educational purposes only**.  

---

## 📚 References
- [Google Admin Toolbox - Message Header Analyzer](https://toolbox.googleapps.com/apps/messageheader/)  
- [MXToolbox - Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx)  
- [Email Authentication (SPF, DKIM, DMARC)](https://dmarc.org/)

