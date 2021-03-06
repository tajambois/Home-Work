# Red Team: Summary of Operations

## Table of Contents
- Exposed Services
- Critical Vulnerabilities
- Exploitation

### Exposed Services

Nmap scan results for target machine reveal services and OS details:

![target 1](https://github.com/tajambois/Home-Work/blob/main/Final%20Project/images/2021-02-22_20h21_56.png)

This scan identifies the services below as potential points of entry:
- Target 1
  - Port 20 - SSH
  - Port - 80 HTTP

The following vulnerabilities were identified on each target:
- Target 1
  - Samba smbd
  - WordPress v. 4.8.15

![Scan](https://github.com/tajambois/Home-Work/blob/main/Final%20Project/images/2021-02-24_20h42_57.png)

### Exploitation
root

The Red Team was able to penetrate `Target 1` and retrieve the following confidential data:
- Target 1
  - `flag1.txt`:
![Flag 1](https://github.com/tajambois/Home-Work/blob/main/Final%20Project/images/flag1.png)
    - **Exploit Used**
      - CWE-200 information disclosure
      - View page source, and located developer note (<!--) left behind.
  - `flag2.txt`
![Flag 2](https://github.com/tajambois/Home-Work/blob/main/Final%20Project/images/flag2.png)
    - **Exploit Used**
      - CWE-521: Weak Password Requirements
      - Password was found on lucky hunch. Hydra could have been used as well.
  - `flag3.txt`:
![Flag 3](https://github.com/tajambois/Home-Work/blob/main/Final%20Project/images/flag3.png)
   - **Exploit Used**
      - CWE-312 Cleartext Storage of Sensitive Information
      - Within the wp-config.php provided MySql username/password information
  - `flag4.txt`:
![Flag4](https://github.com/tajambois/Home-Work/blob/main/Final%20Project/images/flag4.png)
  - **Exploit Used**
      - CWE-284: Improper Access Control
      - `sudo python -c 'import os; os.system("/bin/bash")'`


