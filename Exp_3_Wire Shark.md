# Ex.No.3   Wireshark – Network Packet Capture and Analysis Tool

## Aim
To capture plaintext **login credentials** transmitted over HTTP using **Wireshark**, and analyze how insecure protocols expose sensitive information.

---

##  Step 1: Start Capturing Packets
- Open **Wireshark** in your Windows/Linux machine.  
- Select the active network interface (e.g., **Wi-Fi**).  
- Click the **blue shark fin 🦈** icon to begin capturing packets.  
<p align="center">
 <img width="400" alt="image" src="https://github.com/user-attachments/assets/a12941af-d2e9-47e7-bef0-89c3835e874d" />

</p>
<br>
<p align="center">
<img width="500" alt="image" src="https://github.com/user-attachments/assets/80aa0efc-0e0f-4184-b640-5162ea3ec74a" />
</p>
<br>

---

##  Step 2: Generate Login Traffic
- Open a browser and navigate to a test login page (e.g., `http://testphp.vulnweb.com/login.php`).  
- Enter dummy credentials. For this example:
  
     Username: Tonystark_44
  
     Password: tony@1234

- Submit the form.  
- Even if the login fails, the credentials are **transmitted** in the request.  

<p align="center">
 <img width="500" alt="image" src="https://github.com/user-attachments/assets/a3c7f719-eb84-4066-a9d8-7d554cb71d0d" />

</p>

---

##  Step 3: Stop Capture & Filter HTTP Traffic
- Stop the capture (click the **red square** button).  
- In the display filter bar, type the following filter and press Enter:  

```wireshark
http.request.method == "POST"
```
<p align="center">
    <!--  Screenshot 3: HTTP POST filter applied -->
<img width="500" alt="image" src="https://github.com/user-attachments/assets/e1b268e5-6514-4d18-887b-3d44b07d09bf" />

</p>

##  Step 4: Inspect the POST Packet
- From the filtered list, select the POST packet.
- Expand the following sections in the Packet Details Pane:
     - ->Hypertext Transfer Protocol
     - ->HTML Form URL Encoded

You will see the submitted credentials in plaintext:
  Form item: "uname" = "Tonystark_44"
  Form item: "pass"  = "tony@1234"
<p align="center">
   <img width="500" alt="image" src="https://github.com/user-attachments/assets/9cd09009-8af5-4bfe-a3f2-74e9074d70ef" />

</p>

---
# Rubrics
| Criteria | Mark Allotted | Mark Awarded |
|---|:---:|:---:|
| 1. GitHub Activity & Submission Regularity | 3 | |
| 2. Application of Forensic Tools & Practical Execution | 3 | |
| 3. Documentation & Reporting | 2 | |
| 4. Engagement, Problem-Solving & Team Collaboration | 2 | |
| Total | 10 | |

---

## Result
The experiment successfully captured **login credentials** transmitted via **HTTP**.  
This demonstrates that **HTTP is insecure**, as sensitive information is sent in **plaintext**, making it easy for attackers to intercept.  

---












<br>
<br>

