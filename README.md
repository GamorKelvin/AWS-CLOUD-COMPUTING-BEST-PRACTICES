#  📌Project Overview
This project focuses on how to setup an Amazon S3 bucket and Amazon EC2 instance using aws services and the implemention of security practices that ensure the protection data.

The purpose of this lab is to create a suitable storage cointainer for object,files and also to be able to retrieve at a point need.This lab contains the best security practices that is well suitable to govern or protect the amazon web services.

The lab is configured on S3 bucket and EC2 instance and later addition amazon services will be added 


# 🎯 Ojectives
-  Creation of S3 bucket
-  Learn how to transfer files into the S3
-  Configuration of fill access permission to the bucket
-  creation and configuration of an EC2 Instance
-  Applicaton security and best practice (IAM roles,security groups,bucket policies)

#  🛡️Purpose for the lab
-  file upload
-  objects and files storage
-  Access Permision
-  Best prcatices for security measures
-  Exploration other tools
-  
  ## ⚙️ Lab Configuration

| 🧩 Component       | ⚙️ Configuration   |
| ------------------ | ------------------  |
| 🖥️ Host OS         | Windows 10         |
| 🧠 Host RAM        | 8 GB               |
| ⚡ Processor       | Intel Core i7      |
| 🐉 Security OS     | Windows 10 home    |
| 🧠 Windows RAM     | 2048 MB            |

# 🪜 Lab Setup Procedure for s3 bucket

## Step 1. Create the name of your bucket
The name of the bucket that was meant to stores files was created with name of the practitioner
<img width="2736" height="1824" alt="Gamor bucket" src="https://github.com/user-attachments/assets/a3d9be49-28e0-4840-9026-c98c472c722b" />

## Step 2. Upload your files into the S3 bucket
The files on premise or on your is upload into cloud global reach within a minutes 
<img width="2736" height="1824" alt="S3_02_fullstructure_GAMOR KELVIN" src="https://github.com/user-attachments/assets/2c26431c-3c15-499c-ac93-27069edf74da" />

## Step 3. Create a either a public ip address or private ip address
Public ip makes access whiles private ip makes in internal access or grant access to authorized users
<img width="2736" height="1824" alt="S3_03_Publicwebsite_GamorKelvin" src="https://github.com/user-attachments/assets/f40058ee-239b-4fc5-8fd5-80c56b7bbf8c" />

# 🪜 Lab Setup Procedure for EC2 instance
## Step 1. Creation of an EC2 instance
An ec2 instance are virtual computers in the cloud to run application without buying physical hardware.<img width="2736" height="1820" alt="1 Creation of EC2 instance" src="https://github.com/user-attachments/assets/0865478d-8215-4cf6-b180-b858a8c45e08" />

## Step 2. Configuration of Security Groups
Security group allows inbound and outbound traffic for the ec2 instance,particularly this means cloud pactictitioner has ability file access permission based on users role.
<img width="2736" height="1824" alt="EC2_02_SecurityGroup_Gamorkelvin" src="https://github.com/user-attachments/assets/365a2924-ce40-45f2-9ad1-c474ff3481df" />

## Step 3. SSH LOGIN
This allows a user to securely connect to  a remote EC2 virtual server from his/her local computer using the secure shell (SSH) protocol
<img width="2736" height="1824" alt="EC2_03_SSH_Login_Gamor Kelvin" src="https://github.com/user-attachments/assets/3a81709f-229c-4b5b-a916-d116ad9a2b53" />

## Step 4. Apache Running 
Running apache on an ec2 instance means you are turning that virtual server into live public web server. The apache server acts as the receptionist of for the ec2 instance created; It listens for incoming internet request (like someone typing uniform recource locator URL) and hand back the website files(HTML,images,code) to yours of the browser
<img width="2736" height="1824" alt="EC2_04_Apache running_Gamor Kelvin" src="https://github.com/user-attachments/assets/7078825d-ca4f-4913-9356-c8fd8eda8e14" />

## Step 5.index.html
  Files must be placed in the difficult document root dictory of the installed web server so it can handle incoming HTTP trafic<img width="2736" height="1824" alt="EC2_05_index html_Gamorkelvin" src="https://github.com/user-attachments/assets/554b4a0e-a05e-42b6-a165-154556b7d5d2" />

## Step 6.CURLLOCAALHOST
Running inside a PUTTY terminal helps you check if a web server is actively running locally on a specific EC2 instance and delivering webpage
<img width="2736" height="1824" alt="EC2_06_CURLLOCAALHOST_GamorKelvin" src="https://github.com/user-attachments/assets/aca84374-4906-4f3b-a693-7e67b0c2bde1" />

## Step 7.Public Access
An amazon EC2 public instance is a virtual cloud machine we configured to send and recieved traffic directly over the internet. It can deployed within a public subnet,possesses a public IPV4 address, and utilizes security group rules that allow external access for applicatiion web hosting or remote mangement
<img width="2736" height="1824" alt="EC2_07_Publicaccess_Gamor Kelvin" src="https://github.com/user-attachments/assets/5eb6bb15-4723-4ab6-8bf4-f3b7401c4172" />

# 🔎 Lab Verification

| ✅ Test                        | 🧾 Command                      | 🎯 Expected Result                            |
| ----------------------------- | -------------------------------  | -------------------------------                 |
| 🌐 Login SSH                  | `ec2-user                        | displays a successful EC2 secure login         |
| 📡 Apache Running             | systemctl start httpd`           | appche (httpd) starts succesfully with no error|
| 🌍 Index.html                 | sudo tee /var/www/html/index.html| index,html file is created in the web root     |                   
| 🔎 Curllocaalhost             | curl https://13.50.109.146`      |`Dispaly the content of a webpage(your html)    |                                                                       


# 🐞 Problems Encountered & Solutions

Documenting problems is an important part of the project.

## Problem 1. Putty Logins
After manually configuring the putty settings and wanted to connect it my ec2 instance; I notice"establish connection error. This was depending on the establishment butty the putty terminal and EC2 server configuration.

One workaround used during this lab was:

```bash
echo -e "\n--- EC2 Health Check ---" && echo "User: $(whoami)" && echo "Dir:  $(pwd)" && echo "OS:   $(uname -sr)" && echo -n "Net:  " && (ping -c 1 google.com &>/dev/null && echo "Connected to Internet" || echo "No Internet") && echo -n "Sudo: " && (sudo whoami &>/dev/null && echo "Admin Access OK" || echo "No Admin Access")
```

This code was helped me  to quickly run  and direct dignose checks of the EC2 intance and also verify my username,current folder location, opertaing system version internet connectivity and administrator sudo previleges. This helped me in troubleshooting the issues and the putty server was restarted and started again to be able to have successfull connection.

---
# 💡 What I Learned

Through this project, I learned how to create and configure a virtual environment for cloud practice.

The most important concepts I learned include:

### 1. NAT vs NAT Network

A standard NAT configuration and a NAT Network serve different purposes.

A NAT Network allows multiple VMs connected to the same virtual network to communicate with one another while providing network address translation for external connectivity.

This makes it useful for building a multi-machine cybersecurity laboratory.

### 2. Core Components of an AWS Virtual Private Network

I learned how private virtual network  connect virtual machines to different types of networks and how network configuration affects communication between machines.

### 3.IP Configuration

I learned how to configure and verify IPv4 addressing, subnet masks, gateways, and DNS settings in EC2 instance.

### 4. VM Snapshots

I learned that a clean snapshot should be created **before performing risky or experimental activities**.

This provides a known-good recovery point for future cloucd practition exercises.

### 5. Documentation

I learned that documenting commands, configuration, screenshots, problems, and solutions is an important part of a professional cloud management and  configuration project.

---


# 🔐 Security & Ethical Use

This laboratory is intended for education purposes and with proper authorization

---

# 🔗 Tools & Resources
- Pdf Guide:** [https://docs.aws.amazon.com/pdfs/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02.pdf]
- **Aws console management:** [https://console.aws.amazon.com/]
- **Putty:** [https://www.putty.org/]

  # <img width="100" height="100" alt="WhatsApp Image 2026-09-25 at 7 00 21 AM" src="https://github.com/user-attachments/assets/2c2838c4-9e2c-4066-b4ba-87455c5bfa19" /> Author

**Gamor Kelvin**\
CLF-C02 - AWS Certified Cloud Practitioner - English(ENU)

LinkedIn:[www.linkedin.com/in/gamor-kelvin-7bb588303]


<img width="200" height="200" alt="Gamorkelvin" src="https://github.com/user-attachments/assets/e87842c1-a535-4dcc-8fbc-e7ef12bb99b9" />



Certification:[https://www.credly.com/badges/77edf306-c694-47f3-8d91-aaab6b32965a/]

---

## 📌 Project Information

**Program Name:** Cloud Practitioner at Amilitech | **Weeks:** 12 | **Project:** Configuaration and management of Aamzon S3 Bucket and EC2 instance | **Repository:** GitHub



  














