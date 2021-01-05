## Week 16 Homework Submission File: Penetration Testing 1

#### Step 1: Google Dorking


1. Using Google, can you identify who the Chief Executive Officer of Altoro Mutual is:
- Karl Fitzgerald

2. How can this information be helpful to an attacker:
- Spear Phishing, using social enginnering posing as the CEO will potential have employees click links or other exploits.


#### Step 2: DNS and Domain Discovery

Enter the IP address for `demo.testfire.net` into Domain Dossier and answer the following questions based on the results:

 3. Where is the company located:
   - Sunnyvale, CA

 4. What is the NetRange IP address:
  - 65.61.137.64 - 65.61.137.127

 5. What is the company they use to store their infrastructure:
  - Rackspace Backbone Engineering

 6. What is the IP address of the DNS server:
  - 	65.61.137.117

#### Step 3: Shodan

- What open ports and running services did Shodan find:
- Port: 80 HTTP, 443 HTTPS, 8080 HTTP 

#### Step 4: Recon-ng

- Install the Recon module `xssed`. 
- Set the source to `demo.testfire.net`. 
- Run the module. 

Is Altoro Mutual vulnerable to XSS: 
- YES

![XSS](https://github.com/tajambois/Home-Work/blob/main/Week%2016/Images/XSS.png) 

### Step 5: Zenmap

Your client has asked that you help identify any vulnerabilities with their file-sharing server. Using the Metasploitable machine to act as your client's server, complete the following:

- Command for Zenmap to run a service scan against the Metasploitable machine:
- nmap -T4 -A -v0192.168.0.10
 
- Bonus command to output results into a new text file named `zenmapscan.txt`:

- Zenmap vulnerability script command:
- nmap -T4 -A -v --script sambsa-viln-cve-2012-1182 192.168.0.10

- Once you have identified this vulnerability, answer the following questions for your client:
  1. What is the vulnerability:
  - Samba smbd

  2. Why is it dangerous:
  - Grants an attacker remote access to control machine

  3. What mitigation strategies can you recommendations for the client to protect their server:
  - Turn off these ports.

---
© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.  
