# Crafty-Controller-in-a-Windows-PC
Creating a Minecraft Server in your Windows PC via Crafty Controller and Tailscale for those with a CGNAT Network.

## Step 1: Installing and Running Crafty Controller.
- Downloading ***[Crafty Controller](https://gitlab.com/crafty-controller/crafty-4/-/jobs/7540066681/artifacts/download)*** into your Windows PC.
- Unzip the file in an easy to access folder on your machine. I recommend to unzip it into your desktop.
- Launch the crafty.exe executable.
- Open up a browser to get into the ***Crafty Controller*** webpage.
  > This is your machine's IP address on your homenetwork (192.xxx.xxx.xxx) + the ***Crafty Controller Port*** which is 8443. If you are running the Crafty Controller on a local machine, you can just use localhost to make it easier.
  > Use HTTPS when accessing the webpage.

  > Sample: https://192.xxx.xxx.xxx:8443 or https://localhost:8443.
  
  > You can get the default user login in the default-creds.txt file found in the ***/app/config*** folder.

## Step 2: Changin the password for your admin account.
- Click the ***settings/gear*** icon on the upper right of the webpage. 
- On the ***Panel Config***, locate the ***admin user***. At the end of it should be a ***lock/password icon*** that if you hover your mouse pointer above it, it will say ***new password***. Click it.
- Create a new admin password for the ***Crafty Controller*** webpage.

## Step 3: Setting up Tailscale on your Windows Machine.
> You can use any VPN service you like. But in this case, I'll be sticking with Tailscale as it's a proven VPN for me.
- Go to the ***[Tailscale Website](https://tailscale.com)*** and create an account.
- Download and install the ***[Tailscale Windows Client](https://tailscale.com/download/windows)*** on your Windows machine and login to your account.
- Go to your ***[Tailscale Home Page](https://login.tailscale.com/admin/machines)*** make sure that your machine is listed and appears as connected.

## Step 4: Creating a Minecraft Server in the Crafty Controller webpage.
- In the dashboard at the left side. Click on ***Create New Server***.
  > This will only be a test server for me so you can put in any choice you would like your server to be.
- ***Create New Server***
  ```
  Server Type: Minecraft Server
  Server Select: Vanilla
  Server Version: 1.21.1 (latest)
  Server Name: Test Server
  ```
- ***Quick Settings:***
  ```
  Minimum Memory Size: 1 (in GB)
  Maximum Memory Size: 2 (in GB)
  Server Port: 25565 (Default)
  ```
- Click on ***Build Server***.

## Step 5: Configuring your Minecraft Server.
> Before clicking the start server button. Let's first configure our server.
- Click on the server you just created.
- Go to the ***Config*** tab and scroll down.
- Click on the ***Server Auto Start*** then ***Save***.
  > Optional: Turn the ***Server Crash Detection*** on.
- Go back to the ***Terminal Tab*** and click on the ***Start*** button to start up your server.
- Click ***Yes*** to agree to the ***Minecraft EULA***.
  > Wait for the server to spin up a new ***Minecraft Server***
- 















