This repo contains documentation for two ethical hacking labs performed in a **controlled and authorized lab environment** for educational purposes.

## Labs Included
 SMB Vulnerability Scanning using Enum4Linux

This lab documents:
- Step-by-step procedure
- Commands used
- Screenshots
- Observations and findings

⚠️ Disclaimer:  
All activities were conducted in a lab environment with permission. These techniques must not be used on real systems without authorization.

# Lab SMB-Enum4Linux/


---

# SMB Vulnerability Scanning using Enum4Linux

## Objective
To identify SMB misconfigurations by enumerating users, shares, and permissions on a target system.

## Tools Used
- Nmap
- Enum4Linux
- smbclient

## Lab Setup
- Attacker Machine: Kali Linux
- Target IP Address: 172.17.0.2

---

## Step 1: Network Discovery

```bash
nmap -sN 172.17.0.0/24
```

This scan was used to identify live hosts on the network.

## Step 2: SMB Enumeration using Enum4Linux
1. Enumerate Users
```bash
enum4linux -U 172.17.0.2
```
2. Enumerate Machines
```bash
enum4linux -M 172.17.0.2
```
3. Enumerate SMB Shares
```bash
enum4linux -S 172.17.0.2
```
4. Verbose Share Enumeration
```bash
enum4linux -Sv 172.17.0.2
```
5. Enumerate Password Policy
```bash
enum4linux -P 172.17.0.2
```
6. Full Enumeration
```bash
enum4linux -a 172.17.0.2
```

## Step 3: SMB Share Access using smbclient
1. List Available Shares
```bash
smbclient -L //172.17.0.2/
```
2. Access Print Share
```bash
smbclient //172.17.0.2/print$
```
3. Access Temporary Share
```bash
smbclient //172.17.0.2/tmp
```

## Step 4: File Upload Test (Lab Simulation)

A test file was created to demonstrate how writable SMB shares can be abused.
```bash
nano virus.exe
```

Upload the file while masking the name:
```bash
put virus.exe group_work.txt
```

_**⚠️ The file was not malicious and was used strictly for educational testing.**_

## Findings

1. SMB shares were accessible with weak restrictions

2. Enumeration revealed useful system information

3. Writable shares increase security risk

## Key Takeaways

1. SMB services must be properly secured

2. Enumeration is a critical attack phase

3. Least-privilege access reduces risk

# Conclusion

These labs provided hands-on exposure to common techniques used in real-world cyber attacks, including website cloning through social engineering and SMB service enumeration.

By performing the Website Cloning lab, I gained a clearer understanding of how attackers deceive users through visually convincing fake pages and how easily credentials can be harvested when users do not verify URLs. The SMB Enumeration lab highlighted how misconfigured network services can expose sensitive information such as users, shares, and permissions.

Overall, these exercises reinforced the importance of:
- User awareness and security training
- Proper system and network configuration
- Regular vulnerability assessments
- Ethical responsibility when handling offensive security tools

All activities were conducted strictly in a controlled lab environment for educational purposes. The knowledge gained from these labs will be applied to defensive security practices and ethical penetration testing.
