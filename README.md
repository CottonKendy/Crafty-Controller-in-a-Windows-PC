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

## Step 5: Making sure that you are on the latest JDK Development Kit (23 as of now).
- Click here to go to the ***[Java Download Page](https://www.oracle.com/java/technologies/downloads)***.
- Choose the appropriate version for you. Since I'm on Windows, I chose JDK 23 -> Windows -> x64 Installer
- Install the file.
  > I recommend just letting it install in the default install location.

## Step 6: Configuring your Minecraft Server.
> Before clicking the start server button. Let's first configure our server.
- Click on the server you just created.
- Go to the ***Config*** tab and scroll down.
- Click on the ***Server Auto Start*** then ***Save***.
  > Optional: Turn the ***Server Crash Detection*** on.
- Go back to the ***Terminal Tab*** and click on the ***Start*** button to start up your server.
- Click ***Yes*** to agree to the ***Minecraft EULA***.
  > Wait for the server to spin up a new ***Minecraft Server***

  > If you are using the official Minecraft Launcher. You can try to join the server in your game. IP address should be the same as where the ***Crafty Controller***is running
  > with the port ***25565*** as this is what I assigned it earlier.

  > Since I'm using TLauncher. I would need to change some things on the server.properties.json
- Stop the server once it is done starting since we can't join it yet as we are not on the official Minecraft Launcher.
- Go to the ***Files*** tab and locate the server.properties.
- We will be changing some of our server's properties.
  ```
  This are what I will be chaning, feel free to change the others as you see fit.
    - difficulty=normal
    - level-name=test world
    - motd=My First Minecraft Test Server
    - online-mode=false (this will allow me to join the server even if I'm using TLauncher.)
  After all the editing, click on "Save".
  ```
- After saving the edits we made on our ***server.properties*** file. Go back to the ***Terminal*** tab and click the ***start*** button once again.

## Step 7: Joining your Minecraft Server.
- Open up TLauncher and install the version of Minecraft that is the same with your server. For me it's 1.21.1.
- Enter the game. Go to Multiplayer and click add server.
  ```
  Server Name: Test Server (name it however you like.)
  Server Address: 192.xxx.xxx.xxx:25565 (the ip address of the machine running Crafty Controller + the Minecraft Server port (25565))
  ```
- Click on join

# Enjoy!

# Getting Tailscale to share your Minecraft Server to friends

## Step 1: Go to your ***[Tailscale Home Page](https://login.tailscale.com/admin/machines)***

## Step 2: Locate the Machine your are running Crafty Controller with. Click on share and choose wether you would like to ***share it via email*** or ***copy share link***.
  > I will be using ***copy share link*** on my test server and turning the ***reusable link*** on so I only need to share one link for all my friends.

## Step 3: Copy your machine's Tailscale IP.
- Mine looks like this: 100.xxx.xxx.xxx
- They will be using this ip address when they will try to join your minecraft server.
- Enter the game. Go to Multiplayer and click add server.
  ```
  Server Name: Tailscale Test Server (name it however you like.)
  Server Address: 100.xxx.xxx.xxx:25565 (the Tailscale ip address of the machine running Crafty Controller + the Minecraft Server port (25565))
  ```
- Click Join.

# Enjoy Part 2!
