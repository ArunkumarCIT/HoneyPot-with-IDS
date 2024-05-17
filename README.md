HONETPOT DEPLOYMENT WIITH IDS

BY: ARUNN KUMAR    K

INDEX

1\. Introduction

2\. Setup and Configuration

`    `1. Tools and Technologies Used

`    `2. Steps to Set Up the Honeypot

3\. Implementation

`    `1. Detailed Implementation Steps

4\. Data Collection and Analysis

`    `1. Types of Attacks Detected

`    `2. Data Analysis

5\. Results and Findings

`    `1. Summary of Results

6\. Conclusion

`    `1. Summary



**INTRODUCTION:**

This report details the setup, implementation, and analysis of a honeypot project. The goal of the project is to deploy a honeypot that can attract, detect, and log malicious activities, providing insights into the types of attacks targeting the network.

**2.Setup and Configuration**

**1.Tools and Technologies Used**

The honeypot project utilizes the following tools and technologies:

- Operating System: Kali Linux
- Intrusion Detection System (IDS): Suricata
- Web Application for Exploitation: Damn Vulnerable Web Application (DVWA)

**2.Steps to Set Up the Honeypot**

To set up the honeypot environment, follow these detailed steps:

1. **Install Kali Linux**:
   1. Download the Kali Linux ISO from the official website.
   1. Install Kali Linux on a virtual machine or physical host.
   1. Ensure the system is up-to-date by running


1. **Install and Configure Suricata**:
- Install Suricata:
- Edit the Suricata configuration file (**/etc/suricata/suricata.yaml**) to include network and rule paths.
- And test the modified configuration  and update the configuration file 
- We can also use other predefined rules from various sources and these sources has Community developed rules for configuration and paid versions to
- After modifying the configuration file and updating the rules test it
- Once all the configuration works are done start the suricata
- From the previous test it showed that the alerts are stored in /var/logs/suricata/ as fast.logs and eve.jason files
- To monitor all the alerts in real time we can use the eve.jason file coupled with a tail commad 
- Since the eve.jason file is in jason format we need to install jq tool to view it
- And use the following command to set it up
- To check if is actually detecting the intrusion we can do a simple nmap scan from the attacker machine
- And we can see the alert message displayed
- With this we can conclude that the IDS configuration is done and we can move on to set up a web application to make this machine as  a web server hosting a wesite

**3.Install DVWA for Exploitation**:

- For the web application we are going to use DVWA
- To do this we can start by cloning the DVWA repository from the github to the /var/www/html directory in the machine with the git clone command
- Then we need to modify the user name and password in the configuration file
- Afer that we need to configure the data base so that the username and password can be verified
- To do that we need to start mysql server
- And login as root to grant previlage and authentication to the new user
- After the database configuration we can visit the website through web browser

**4.Data Collection and Analysis**

**Types of Attacks Detected**

1. **Port Scans**: Detected using Suricata logs.
1. **Web Exploits**: Captured using DVWA and Suricata.

**Data Analysis:**

Port Scans: Analyzed logs to identify source IP addresses and scan patterns.

Web Exploits: Used DVWA logs to understand attack vectors and methods.

**5.Results and Findings**

**Summary of Results**

Detected multiple port scans originating from various IP addresses.

Identified common web exploit attempts, including SQL injection and XSS.

**6.Conclusion**

**Summary**

The honeypot project successfully detected and logged various types of attacks, providing valuable insights into the attack methods and sources targeting the network.



