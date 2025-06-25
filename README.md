## CyberDefenders-Lab-Write-up-Tomcat-Takeover

## Scenario

The SOC team identified suspicious activity on a web server within the company’s intranet. To investigate, network traffic was captured and analyzed for signs of malicious activity that may have compromised the Apache Tomcat server.

---

## Tools Used

- **Wireshark** – Network packet analysis  
- **whatsmyipaddress.com** – IP geolocation lookup

---

## Analysis Summary

During analysis, I identified the **attacker's IP address** and **location**. The attacker performed an **active port scan** and discovered several open ports — notably **port 8080**, commonly used for web admin panels. From there, the attacker accessed the web server's **admin interface**.

---

## Attack Flow

1. **Reconnaissance:**  
   The attacker performed a port scan to enumerate open services.

2. **Directory Discovery:**  
   Using the tool **Gobuster**, the attacker revealed several directories, including `/manager`.

3. **Credential Access:**  
   After discovering the manager panel, the attacker gathered credentials and **brute-forced** access to the admin panel.

4. **Reverse Shell Deployment:**  
   Upon gaining access, the attacker uploaded a malicious `.war` file (`JXQOZY.war`) to **establish a reverse shell**, allowing remote access into the server.

5. **Persistence:**  
   A script was executed to maintain the attacker’s presence on the compromised system.

---

## Conclusion

The identified **Indicators of Compromise (IoCs)** suggest the following escalation process:

- Escalate the case to the **Incident Response Team**  
- Proceed with **containment**, **forensics**, and **eradication**  
- Submit findings to **compliance** for reporting and policy review
- 
