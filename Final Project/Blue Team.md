# Blue Team: Summary of Operations

## Table of Contents
- Network Topology
- Description of Targets
- Monitoring the Targets
- Patterns of Traffic & Behavior
- Suggestions for Going Further

### Network Topology
The following machines were identified on the network:
- TARGET1
  - **Operating System**: Linux
  - **Purpose**: Webserver
  - **IP Address**: 192.168.1.110
- TARGET2
  - **Operating System**: Linux
  - **Purpose**: Webserver
  - **IP Address**: 192.168.1.115
- Capstone
  - **Operating System**: Linux
  - **Purpose**: Webserver
  - **IP Address**: 192.168.1.105
 - ELK
   - **Operating System**: Linux
   - **Purpose**: Event Logging
   - **IP Address**: 192.168.1.100
 - Kali
   - **Operating System**: Linux
   - **Purpose**: Attack Machine
   - **IP Address**: 192.168.1.90

### Description of Targets

The target of this attack was: `Target 1` (192.168.1.110).

Target 1 is an Apache web server and has SSH enabled, so ports 80 and 22 are possible ports of entry for attackers. As such, the following alerts have been implemented:

### Monitoring the Targets

Traffic to these services should be carefully monitored. To this end, we have implemented the alerts below:

#### Excessive HTTP Errors
This alert is implemented as follows:
  - **Metric**: HTTP Errors
  - **Threshold**: 400 Errors, top five, within 5 minutes
  - **Vulnerability Mitigated**: Directory Busting
  - **Reliability**: Medium

#### HTTP Request Size Monitor
This alert is implemented as follows:
  - **Metric**: HTTP Size
  - **Threshold**: 3500 Requests
  - **Vulnerability Mitigated**: Server Side Validation
  - **Reliability**: Medium

#### CPU Usage Monitor
this alert is implemented as follows:
  - **Metric**: CPU Usage
  - **Threshold**: 0.5
  - **Vulnerability Mitigated**: Brute Froce
  - **Reliability**: Medium

![alerts](https://github.com/tajambois/Home-Work/blob/main/Final%20Project/images/2021-02-22_19h35_12.png)

