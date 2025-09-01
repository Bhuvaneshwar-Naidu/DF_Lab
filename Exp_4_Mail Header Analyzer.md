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
<br>
<img width="1919" height="1150" alt="image" src="https://github.com/user-attachments/assets/d31cd4bd-21f4-4ea7-808c-1e84c642cbf1" />
<br>
---


### Step 2: Copy the Email Header
- Copy the entire header text (contains details like `Received`, `Message-ID`, `SPF`, `DKIM`, etc.)
- Save it into a text file or keep it ready to paste into an analysis tool.
<br>
<img width="1916" height="1140" alt="image" src="https://github.com/user-attachments/assets/d130d61b-0f2d-4135-b310-f8fb31369732" />
<br>
---

### Step 3: Use Mail Header Analyzer (MHA)
1. Open [Google Admin Toolbox MHA](https://toolbox.googleapps.com/apps/messageheader/)  
2. Paste the copied email header into the text box.  
3. Click **Analyze the Header**.
<br>
<img width="1919" height="1058" alt="image" src="https://github.com/user-attachments/assets/80ce5cb8-16f9-4ff1-a665-71acf0125760" />
<br>

---

### Step 4: Interpret the Results
- **Received Chain** → Shows the exact path (servers & timestamps) the email took.
  - The email went through the following servers:
    - **r182.inswa.coca-cola.com** → **Google Mail Server (mx.google.com)**, taking **5 minutes** for delivery.
    - Further SMTP relays from Google IP addresses.

- **Delay Analysis** → Highlights unusual delays that might indicate suspicious routing.
  - There is a delay of **5 minutes** before the email was received by the final server. This isn't too unusual, but it’s worth considering depending on the context of the email delivery.

- **SPF/DKIM/DMARC** → Shows authentication results.
   - **SPF**: ✅ **Pass** → Email was sent from an authorized IP (20.96.233.182).
   - **DKIM**: ✅ **Pass** → The email domain (inswa.coca-cola.com) has verified the message's integrity.
   - **DMARC**: ✅ **Pass** → The email aligns with the domain's policy.

- **Message-ID** → Should match the sender’s domain; mismatch may indicate forgery.
  - The **Message-ID** appears legitimate and corresponds to the sender's domain (inswa.coca-cola.com), meaning it's unlikely to be forged.
<br>
<img width="1918" height="1050" alt="image" src="https://github.com/user-attachments/assets/04c7d641-7b21-427e-ac2c-af5de1c7b7fd" />
<br>

---

## ✅ Conclusion:
Successfully analyzed the email header. All authentication checks (SPF, DKIM, DMARC) **passed**, indicating the email is **genuine**. The **delay** is not unusually long and doesn’t suggest suspicious activity.
  

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

