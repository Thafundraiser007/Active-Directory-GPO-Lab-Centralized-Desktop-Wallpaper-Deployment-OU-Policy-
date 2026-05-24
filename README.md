# Active-Directory-GPO-Lab-Centralized-Desktop-Wallpaper-Deployment-OU-Policy-
This lab demonstrates how to configure a Group Policy Object (GPO) in Active Directory to deploy a centralized desktop wallpaper across all users within a specific Organizational Unit (OU). It includes policy creation, linking, testing, and verification steps to ensure consistent desktop environment settings across domain-joined computers



# Active Directory GPO Lab – Centralized Desktop Wallpaper Deployment

## 📌 Overview
This lab demonstrates how to configure a Group Policy Object (GPO) in Active Directory to deploy a centralized desktop wallpaper to all users within a specific Organizational Unit (OU).

It shows how domain administrators can enforce consistent desktop settings across multiple computers.

---

## 🖥️ Environment
- Windows Server (Active Directory Domain Services installed)
- Windows 10/11 Domain-Joined Client Machines
- Group Policy Management Console (GPMC)
- Shared Network Folder (for wallpaper storage)

---

## 🎯 Objective
- Create and configure a Group Policy Object (GPO)
- Apply it to a specific Organizational Unit (OU)
- Deploy a standardized desktop wallpaper
- Verify policy application on client machines

---

## ⚙️ Configuration Steps

### 1. Prepare Wallpaper File
- Select an image to use as the wallpaper
- Store it in a shared network folder:

\\SERVERNAME\SharedFolder\wallpaper.jpg

- Ensure all domain users have read access

---

### 2. Create and Link GPO
- Open Group Policy Management (GPMC)
- Navigate to your domain
- Right-click the target OU
- Click: Create a GPO in this domain, and Link it here
- Name the GPO: Desktop Wallpaper Policy

---

### 3. Configure Wallpaper Policy
- Edit the GPO
- Navigate to:
User Configuration → Administrative Templates → Desktop → Desktop → Desktop Wallpaper

- Enable the policy
- Set wallpaper path:

\\SERVERNAME\SharedFolder\wallpaper.jpg

- Choose wallpaper style (Fill / Stretch / Center)

---

### 4. Apply Policy on Client Machine
Run:

gpupdate /force

Or restart the computer.

---

### 5. Verify Policy Application
Run:

gpresult /r

Check that the GPO is listed under Applied Group Policy Objects

---

## 📸 Evidence
- Screenshot of GPO settings
- Client desktop showing applied wallpaper
- gpresult output confirming policy application

---

## 🧠 What I Learned
- How Group Policy Objects work in Active Directory
- How to apply policies to Organizational Units (OUs)
- How to use shared network paths in GPO
- How to verify policy application using gpresult

---

## 🚀 Future Improvements
- Apply different wallpapers per department OU
- Use security filtering for specific users/groups
- Combine with login scripts for automation

---

## 👤 Author
Jamill Naipao – Network & Systems Administration Student
