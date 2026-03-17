# 🚀 Hybrid Infrastructure Monitoring using AWS CloudWatch
Implemented hybrid monitoring by integrating an on-prem VM with AWS CloudWatch using CloudWatch Agent. Created dashboards and alarms, enabling centralized visibility and real-time alerts via SNS for both cloud and on-prem infrastructure.

## 📌 Project Overview

This project demonstrates a **Hybrid Monitoring Architecture** where an on-premise server (VM) is integrated with AWS CloudWatch for centralized monitoring and alerting.

The system collects metrics from:

* ☁️ AWS EC2 instance
* 🖥️ On-Premise VM

and displays them in a **single CloudWatch dashboard** with alerting via SNS.

---

## 🧠 Architecture

```
On-Prem VM → CloudWatch Agent → AWS CloudWatch
                                  ↓
EC2 Instance → CloudWatch Metrics → Dashboard + Alarm → SNS Email Alert
```

<img width="1536" height="1024" alt="ChatGPT Image Mar 17, 2026, 07_09_42 PM" src="https://github.com/user-attachments/assets/0901baa9-6d42-44e3-966b-c6dc7f48a5ee" />


---

## 🛠️ Technologies Used

* AWS CloudWatch
* AWS EC2
* AWS SNS
* IAM
* Ubuntu (VM)
* CloudWatch Agent

---

## ⚙️ Project Setup Steps

### 🔹 1. On-Prem VM Setup

* Created Ubuntu VM using VirtualBox
* Installed CloudWatch Agent

📸 Screenshot:



<img width="1032" height="515" alt="Screenshot 2026-03-15 135444" src="https://github.com/user-attachments/assets/a58c1eb5-981b-4dcb-ba3a-8747a357b9df" />




<img width="1029" height="979" alt="Screenshot 2026-03-17 202809" src="https://github.com/user-attachments/assets/181403e9-9c00-4159-aac6-2130eb173a86" />



---

### 🔹 2. EC2 Instance Setup

* Launched EC2 instance (Ubuntu)
* Attached IAM Role with CloudWatch permissions

📸 Screenshot:


<img width="1874" height="1199" alt="Screenshot 2026-03-15 141147" src="https://github.com/user-attachments/assets/0fa8c498-50c7-49a4-a69a-4bd77d6d5743" />



<img width="1875" height="1199" alt="Screenshot 2026-03-15 142733" src="https://github.com/user-attachments/assets/2e1a7605-43c9-4b0e-bf3c-aa196e64dca4" />


---

### 🔹 3. CloudWatch Agent Configuration

* Configured agent on both EC2 and VM
* Collected metrics:

  * CPU
  * Memory
  * Disk

📸 Screenshot:
![Config File](docs/config-file.png)

<img width="1280" height="800" alt="new5 6" src="https://github.com/user-attachments/assets/3e30e5a9-5491-4c80-a3d7-1e2efbe5c28c" />



<img width="1920" height="1200" alt="new5 1" src="https://github.com/user-attachments/assets/c14dd1bc-adc2-40f0-b362-c54e45dcfabe" />



---

### 🔹 4. Agent Running Verification

* Started CloudWatch agent
* Verified service status

📸 Screenshot:



<img width="1280" height="800" alt="new5 3" src="https://github.com/user-attachments/assets/37480ae6-7fe9-41b0-96fc-9699688401a1" />






---

### 🔹 5. Metrics Verification

* Verified metrics in CloudWatch
* EC2 metrics → CPUUtilization
* VM metrics → mem_used_percent

📸 Screenshot:


<img width="1883" height="1199" alt="Screenshot 2026-03-17 180257" src="https://github.com/user-attachments/assets/adfa24d8-39ed-4c6b-9fcd-9a83e27fb8e5" />



---

### 🔹 6. Dashboard Creation

* Created CloudWatch Dashboard:

  * EC2 CPU
  * VM Memory
  * VM Disk

📸 Screenshot:

<img width="1875" height="1199" alt="Screenshot 2026-03-17 205611" src="https://github.com/user-attachments/assets/34671999-66ec-4058-aca6-993d57f61635" />







---

### 🔹 7. SNS Notification Setup

* Created SNS Topic
* Subscribed email for alerts

📸 Screenshot:





<img width="1875" height="1194" alt="Screenshot 2026-03-17 210008" src="https://github.com/user-attachments/assets/0ec96db4-95a0-4127-9a46-40dc52ec8666" />


<img width="1858" height="1199" alt="Screenshot 2026-03-17 190142" src="https://github.com/user-attachments/assets/9e7119f0-fdb4-4fb8-98f8-e08ccf3ea1ce" />






---

### 🔹 8. Alarm Configuration

* Created alarm:

  * EC2 CPU > 70%
  * VM Memory > 70%

📸 Screenshot:



<img width="1868" height="1199" alt="Screenshot 2026-03-17 210343" src="https://github.com/user-attachments/assets/b7f0bccc-bc22-43b7-9a69-217cd0f00452" />






---

### 🔹 9. Testing (Stress Load)

* Generated load using stress command
* Verified:

  * Metric spike
  * Alarm triggered
  * Email received

📸 Screenshot:


<img width="1874" height="1199" alt="Screenshot 2026-03-17 185925" src="https://github.com/user-attachments/assets/c8087bf7-253d-40ec-b412-fda483d5116c" />



<img width="1861" height="1199" alt="Screenshot 2026-03-17 190106" src="https://github.com/user-attachments/assets/fff19c35-b497-41a5-81f4-2dcfff5551fc" />








---

## 📊 Final Outcome

* Centralized monitoring of hybrid infrastructure
* Real-time metric visualization
* Automated alerting system
* Successfully validated monitoring using stress testing

---

## 💬 Key Learnings

* Hybrid cloud monitoring architecture
* CloudWatch Agent configuration
* Custom metrics collection
* Dashboard and alert setup
* Troubleshooting real-world issues

---

## 🎯 Conclusion

This project successfully demonstrates how to integrate on-premise infrastructure with AWS monitoring services to achieve centralized visibility and proactive alerting.

---

## 👨‍💻 Author

**Shreyash Meshram**
