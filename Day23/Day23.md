# Day 23: Automating User Data Configuration Using the CLI

# Step1: Check the resource and location

$ az group list

# Step2: Create a user script to automate the custom user data setup

$ vi nginx-setup.txt

#cloud-config

package_upgrade: true

packages:
  - nginx

runcmd:
  - systemctl start nginx
  - systemctl enable nginx

# Step3: Create VM

az vm create \
  --resource-group kml_rg_main-5d4147725f504549 \
  --name datacenter-vm \
  --image Ubuntu2204 \
  --admin-username azureuser \
  --generate-ssh-keys \
  --custom-data nginx-setup.txt \
  --size Standard_B1s \
  --storage-sku Standard_LRS \
  --public-ip-sku Standard

  # Step4: Open port 80 (HTTP)

  az vm open-port \
  --resource-group kml_rg_main-5d4147725f504549 \
  --name datacenter-vm \
  --port 80 \
  --priority 800

  # Step5: Get public IP of VM to verify

  az vm show \
  --resource-group kml_rg_main-5d4147725f504549 \
  --name datacenter-vm \
  -d \
  --query publicIps \
  -o tsv

  #Copy IP and open in browser OR CURL in terminal ( $ curl http://pub-ip)
