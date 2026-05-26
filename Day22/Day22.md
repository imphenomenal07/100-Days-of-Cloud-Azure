# Day 22: Configuring Instances with User Data

# Step1: Login into Azure Console

# Step2: Create VM with UserData

# Basics

**Subscription** - Azure Free Labs
**Resource group** - kml_rg_main-033f4968831b4695
**Virtual machine name** - nautilus-vm
**Region** - East US
**Availability options** - No infrastructure redundancy required
**Zone options** - Self-selected zone
**Security type** - Standard
**Image** - Ubuntu Server 24.04 LTS - Gen2
**VM architecture** - x64
**Size** - Standard B1s (1 vcpu, 1 GiB memory)
**Enable Hibernation** - No
**Authentication type** - Password
**Username** - azureuser
**Public inbound ports** - SSH, HTTP, HTTPS

# Advanced

**Custom User Data:**

#!/bin/bash
sudo apt update
sudo apt install nginx -y
sudo apt enable nginx
sudo apt start nginx

**Review + Create**

# Step3: Access Nginx via browser

Resource created ➡️ Copy Public IP ➡️ Paste in browser and hit enter ➡️ Click on **Continue to the site**

# Step4: Check connectivity via Azure client

Run the below command on Azure Client:

$ curl http://vm-public-ip
