
# POC on Dynamic Application Security Testing (DAST) for Golang Application

<div align="center">
  <img src="https://th.bing.com/th/id/OIP.QunIT057-418jErIF4NAogHaGi?rs=1&pid=ImgDetMain" width="40%"/>
</div>

| Last updated | Version | Author         | Comment         | Reviewer |
| ------------ | ------- | -------------- | --------------- | -------- |
| 21-05-2025   | V1    | Prateek Rai | Internal Review | Siddharth Pawar   |

# **Table of Content:**

* [Introduction](#introduction)
* [Pre-requisites](#pre-requisites)
* [Step-by-Step Setup Guide](#step-by-step-setup-guide)
* [Conclusion](#conclusion)
* [Contacts](#contacts)
* [Reference](#reference)

---

# **Introduction**

This Proof of Concept (POC) outlines the steps to perform Dynamic Application Security Testing (DAST) using **OWASP ZAP** on a **Golang-based web application**. DAST is essential for identifying runtime vulnerabilities in web applications without accessing source code.

---

# **Pre-requisites**

* Installed Java 17 or higher (Required for OWASP ZAP).
* A running Golang-based web application (e.g., REST API or web server).

> **NOTE:**
> We are using a sample **Go Web API** application for DAST.
> Refer to this [Sample Golang API Repository](https://github.com/snaatak-Downtime-Crew/Documentation/blob/SCRUMS-78-YUVRAJ/ot-ms-understanding/applications/employee/poc/README.md) for setup and usage.

![image](https://github.com/user-attachments/assets/67ff3d0b-4232-4d3b-9f83-87bc30d46bc9)


---

# **Step-by-Step Setup Guide**

### **Step 1: Install OWASP ZAP**

> To install OWASP ZAP, follow the instructions in the referenced guide.
> 👉 [Install OWASP ZAP Commands](https://github.com/snaatak-Downtime-Crew/Documentation/blob/SCRUMS-160-Durgesh/application-ci/checks/java/dast/poc/README.md#step-by-step-installation-guide)

---

### **Step 2: Start an Automated Scan**

1. Launch OWASP ZAP.
2. Click on **Automated Scan**.
3. Provide the URL of the running Golang application (e.g., `http://localhost:8080`).
4. Click on **Attack**.

OWASP ZAP will begin scanning your Go application for common web vulnerabilities.

![image](https://github.com/user-attachments/assets/211ff50b-a0ef-4e34-abc6-d33659e41921)



---

### **Step 3: Analyze Scan Results**

Once the scan completes:

* Go to the **Alerts** tab.
* Review each alert to understand vulnerabilities found such as:

  * Vulnerable JS Libraray
  * Content Security Policy (CSP) Header Not Set
  * Missing Anti-clickjacking Header
  * Timestamp Disclosure- Unix(70)

![image](https://github.com/user-attachments/assets/27a3f4ca-0c82-4999-84a4-d9034e768d9e)


---

### **Step 4: Generate a Report**

1. Go to **Report** in the menu.
2. Choose the desired format: **HTML**, **PDF**, or **JSON**.
3. Click on **Generate Report**.
4. Save the report in your desired directory.

This report is useful for team review or auditing purposes.

![image](https://github.com/user-attachments/assets/e5199663-5308-4390-bb87-a58d107018b5)

---

### **Step 5: Open this Report in web browser to see results**
Here you can see results as given below:

![image](https://github.com/user-attachments/assets/4b5864f5-7517-40dc-bf69-782bab886db0)

![image](https://github.com/user-attachments/assets/f037b207-f060-46c1-ae46-cd3ef3bc3a7b)



# **Conclusion**

By integrating **OWASP ZAP** with a Golang-based application, you can effectively simulate attacks, identify vulnerabilities, and enhance the overall security posture of your API or web service. This POC serves as a reference to incorporate DAST in your CI/CD pipeline or manual testing routines.

---

# **Contacts**

| Name               | Email Address                                                                         |
| ------------------ | ------------------------------------------------------------------------------------- |
| **Prateek Rai** | [prateek.rai.snaatak@mygurukulam.co](mailto:prateek.rai.snaatak@mygurukulam.co) |

---

# **Reference**

| Links                                                                                                  | Description                                                 |
| ------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------- |
| [How to install OWASP ZAP](https://techofide.com/blogs/how-to-install-owasp-zap-on-windows-and-linux/) | Step-by-step OWASP ZAP installation guide for Windows/Linux |
| [OWASP ZAP Official Site](https://www.zaproxy.org/)                                                    | Official documentation, downloads, and tutorials            |

