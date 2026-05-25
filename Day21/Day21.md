# Day 21: Assigning Public IP to Virtual Machines

# Step1: Login into Azure Console

# Step2: Create VM the required configurations

Home ➡️ Virtual Machines ➡️ Create

Fill the require details like Name, Access-key, Region, Size, Disk

# Static Public IP:
Create and Attach public IP while creating VM

#Once all done, create VM

# Step3: Login into VM via GitBash terminal or other terminal

$ ssh -i ~/access-key-location/key-name.pem azureuser@static-public-IP

# Step4: Configure access via Azure-client terminal

1. Create public key:
   $ ssh-keygen -t rsa

2. Go to require directory:
   $ cd .ssh

3. Copy content of public key:
   $ cat rsa_id.pub

# Step4: Setup access

1. Go the GitBash terminal where you have logged into Azure VM:

2. Go the require directory:
   $ cd .ssh

3. Paste public key content:
   $ vi authorized_keys

   Paste key content, save and exit:

# Step5: Login via Azure client

$ ssh azureuser@public-IP

# If there is any access issues via Azure client, make sure you have set up access key correctly!!
