# Ex.No.3   Wireshark – Network Packet Capture and Analysis Tool

## 🎯 Aim
To capture plaintext **login credentials** transmitted over HTTP using **Wireshark**, and analyze how insecure protocols expose sensitive information.

---

## 🔹 Step 1: Start Capturing Packets
- Open **Wireshark** in your Windows/Linux machine.  
- Select the active network interface (e.g., **Wi-Fi**).  
- Click the **blue shark fin 🦈** icon to begin capturing packets.  

<br>
<br>
<p align="center">
  <img width="1919" height="1199" alt="Figure 1: Wireshark Interface Selection" src="IMAGE_LINK_HERE" />
</p>
<br>
<br>

---

## 🔹 Step 2: Generate Login Traffic
- Open a browser and navigate to a test login page (e.g., `http://testphp.vulnweb.com/login.php`).  
- Enter dummy credentials. For this example:
  
     Username: Tonystark_44
  
     Password: tony@1234

- Submit the form.  
- Even if the login fails, the credentials are **transmitted** in the request.  

<br>
<br>
<p align="center">
  <!-- 🟩 Screenshot 2: Login form filled -->
  <img width="1916" height="1149" alt="Login Form Example" src="IMAGE_LINK_HERE" />
</p>
<br>
<br>

---

## 🔹 Step 3: Stop Capture & Filter HTTP Traffic
- Stop the capture (click the **red square** button).  
- In the display filter bar, type the following filter and press Enter:  

```wireshark
http.request.method == "POST"
```


<br>
<br>
<p align="center">
    <!-- 🟩 Screenshot 3: HTTP POST filter applied -->
    <img width="1919" height="1199" alt="HTTP POST Filter Applied" src="IMAGE_LINK_HERE" />
</p>

## 🔹 Step 4: Inspect the POST Packet
- From the filtered list, select the POST packet.
- Expand the following sections in the Packet Details Pane:
     - ->Hypertext Transfer Protocol
     - ->HTML Form URL Encoded

You will see the submitted credentials in plaintext:
  Form item: "uname" = "Tonystark_44"
  Form item: "pass"  = "tony@1234"
<br>
<br>
<p align="center">
    <img width="1919" height="1199" alt="Figure 4: Captured Credentials" src="IMAGE_LINK_HERE" />
</p>
<br>
<br>

## ✅ Result
The experiment successfully captured **login credentials** transmitted via **HTTP**.  
This demonstrates that **HTTP is insecure**, as sensitive information is sent in **plaintext**, making it easy for attackers to intercept.  

---

## 📌 Notes
- Always use **HTTPS** to protect credentials from being intercepted.  
- This experiment is for **educational purposes only**.  
- Unauthorized sniffing of network traffic is **illegal and unethical**.  

---

## 📚 References
- [Wireshark Official Documentation](https://www.wireshark.org/docs/)  
- [HTTP Protocol Analysis](https://developer.mozilla.org/en-US/docs/Web/HTTP)  










<br>
<br>

