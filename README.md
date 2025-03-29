# Web Application Scanning with Nikto

##  Project Overview
This project demonstrates how to use **Nikto** to scan a web application for vulnerabilities.

## 🛠 Tools Used
- **Nikto** (Web Vulnerability Scanner)
- **Kali Linux**
- **OWASP Juice Shop** (Test Environment)

## Install Nikto
### **Nikto is pre-installed on Kali Linux, but if not, install it using:** **```sudo apt update&& sudo apt upgrade```**
![kali-linux-2024 4-vmware-amd64-2025-03-23-12-24-38](https://github.com/user-attachments/assets/c03aa9d7-5e58-490c-8f29-57bf634de554)
### **```sudo apt install nikto```**
![kali-linux-2024 4-vmware-amd64-2025-03-23-12-49-09](https://github.com/user-attachments/assets/48147ca8-d20f-4c4c-8415-4bc80fdf1e84)
## Run a Basic Scan

### Start scanning your vulnerable web application: **```nikto -h http://localhost:3000```**
![kali-linux-2024 4-vmware-amd64-2025-03-23-17-21-52](https://github.com/user-attachments/assets/742ba78e-4e79-4772-a31d-1581cf9cf62c)
![kali-linux-2024 4-vmware-amd64-2025-03-23-17-22-34](https://github.com/user-attachments/assets/dd55beda-1da5-42f5-a997-759e5e828f85)
![kali-linux-2024 4-vmware-amd64-2025-03-23-17-27-10](https://github.com/user-attachments/assets/ce2af7e2-9f4f-465e-a0ba-279cb49382e1)
![kali-linux-2024 4-vmware-amd64-2025-03-23-17-27-31](https://github.com/user-attachments/assets/2813278f-13d3-4a13-9e7e-9aadad39dc48)
![kali-linux-2024 4-vmware-amd64-2025-03-23-17-27-53](https://github.com/user-attachments/assets/bd2b9574-ac27-4db3-9dcf-5bec091af729)
### Explanation:
### ```-h``` → Specifies the target host.
**:one:Expected Output:**

**:two:Checks for outdated software.**

**:three: Detects misconfigurations.**

**:four: Lists security headers missing.**

**:five: Finds default credentials.**

## Advanced Scanning Techniques
### 1️⃣ Full-Port Scan with Nikto & Nmap
### First, find open ports using Nmap:```nmap -p- localhost```
![kali-linux-2024 4-vmware-amd64-2025-03-23-17-30-53](https://github.com/user-attachments/assets/f0fe0649-d92d-4c33-9e04-e44b791969aa)

### 2️⃣ Run a More Aggressive Scan
### Use the -Tuning option to focus on specific vulnerabilities:```nikto -h http://localhost:3000 -Tuning x```

![kali-linux-2024 4-vmware-amd64-2025-03-23-17-33-14](https://github.com/user-attachments/assets/9acfaeee-990a-43ce-8c5c-eb75dc5ace58)
![kali-linux-2024 4-vmware-amd64-2025-03-23-17-33-47](https://github.com/user-attachments/assets/dadd1e96-eb55-499a-af23-4fdbc5fa5e31)
![kali-linux-2024 4-vmware-amd64-2025-03-23-17-34-10](https://github.com/user-attachments/assets/2c898218-8bf2-41b5-98b5-40768604f107)
![kali-linux-2024 4-vmware-amd64-2025-03-23-17-34-22](https://github.com/user-attachments/assets/bff9c6fb-5adb-427b-aa80-255c134cd089)
### Tuning Options:

**1 → Interesting files (e.g., robots.txt)**

**2 → Server misconfigurations**

**4 → Injection flaws (SQLi, XSS)**

**x → Full scan**

### 3️⃣: Scan HTTP Websites (OWASP Juice Shop Example)
### **If your target runs on HTTP (like OWASP Juice Shop), use the following command:** **```nikto -h http://localhost:3000```**
### **If the application is hosted on a remote machine, replace localhost with the target IP address:**
![kali-linux-2024 4-vmware-amd64-2025-03-28-18-12-55](https://github.com/user-attachments/assets/5ec21480-d021-42d6-8e79-b713ac401430)
![kali-linux-2024 4-vmware-amd64-2025-03-28-18-15-03](https://github.com/user-attachments/assets/87c6f378-0e7d-4fda-8e16-bea6591d97d4)
![kali-linux-2024 4-vmware-amd64-2025-03-28-18-15-42](https://github.com/user-attachments/assets/7cc15c28-c06c-4c25-adc7-861dfd9c4660)

### 4️⃣ Scan Using a Custom User-Agent
### Some WAFs block scanners based on the user-agent. Bypass this by spoofing a browser:```nikto -h http://localhost:3000 -useragent "Mozilla/5.0 (Windows NT 10.0; Win64; x64)"```
![kali-linux-2024 4-vmware-amd64-2025-03-23-17-40-58](https://github.com/user-attachments/assets/56e538ca-e3b8-43bf-a11d-4504ebdc4901)
![kali-linux-2024 4-vmware-amd64-2025-03-23-17-41-10](https://github.com/user-attachments/assets/76f6ed89-fc5a-497d-a35f-592753039676)
![kali-linux-2024 4-vmware-amd64-2025-03-23-17-41-21](https://github.com/user-attachments/assets/cb4b8e24-1f0f-4610-b529-eba297a92817)
![kali-linux-2024 4-vmware-amd64-2025-03-23-17-41-30](https://github.com/user-attachments/assets/13c1ab11-2831-4b03-be6e-b9c39307cb34)
![kali-linux-2024 4-vmware-amd64-2025-03-23-17-44-18](https://github.com/user-attachments/assets/a90963f2-ef05-4570-a107-59a517b6fb19)
### 5️⃣ Save the Scan Report
### Save results in HTML, CSV, XML, or JSON format:```nikto -h http://localhost:3000 -o scan_results.html -Format html```
![kali-linux-2024 4-vmware-amd64-2025-03-23-17-54-27](https://github.com/user-attachments/assets/a401e6c6-a8b8-4c49-86ca-ad99c86c8fd2)
![kali-linux-2024 4-vmware-amd64-2025-03-23-17-55-16](https://github.com/user-attachments/assets/99c1bf93-460f-479f-89d4-39e8c27c0ede)
### Other formats:
### ```-Format csv```
### ```-Format xml```
### ```-Format json```


 
