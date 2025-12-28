Here’s a clean, rewritten version of your lab report without the emojis and with a professional, concise style:

---

# Vulnerability Scanning with Nikto

## Objective

The purpose of this lab is to perform web server vulnerability scanning using Nikto, identify potential security misconfigurations and vulnerabilities, and analyze the results in a controlled lab environment.

## Tools Used

* Kali Linux
* Nikto Web Vulnerability Scanner
* Nano text editor
* Web browser (Firefox)

## Lab Environment

* Target IP addresses hosted within a private lab network
* Web services running on selected hosts

## Step-by-Step Procedure

### 1. Create Target IP List

Create a file containing the IP addresses to scan:

```bash
nano ip_list.txt
```

Add the following IP addresses:

```text
10.6.6.14
10.6.6.1
10.6.6.13
10.6.6.23
172.17.0.2
```

Save and exit the file.

### 2. Run Nikto Scan on Multiple Targets

Scan all IPs listed in the file:

```bash
nikto -h ip_list.txt
```

### 3. Scan a Specific Target and Generate HTML Report

Perform a focused scan and save the output as an HTML report:

```bash
nikto -h 172.17.0.2 -o scan_results.html
```

### 4. Locate and Open the Scan Results

* Locate the output file:

```bash
locate scan_results.html
```

* Open the report in a browser to view detailed results.

## Key Findings & Observations

1. Detection of outdated server software
2. Identification of insecure HTTP headers
3. Presence of default files and directories
4. Potential exposure to known vulnerabilities (CVE references)

These findings indicate weak server hardening and poor security configuration.

## Conclusion

Nikto successfully identified multiple web server weaknesses that could be exploited if not addressed. Regular vulnerability scanning is recommended to maintain proactive security.


