## Unit 18 Homework: Lets go Splunking!

### Step 1: The Need for Speed 

**Task:** Create a report to determine the impact that the DDOS attack had on download and upload speed. Additionally, create an additional field to calculate the ratio of the upload speed to the download speed.


1.  Upload the following file of the system speeds around the time of the attack.
    - [Speed Test File](resources/server_speedtest.csv)

2. Using the `eval` command, create a field called `ratio` that shows the ratio between the upload and download speeds.
   - Hint: The format for creating a ratio is: `| eval new_field_name = 'fieldA'  / 'fieldB'`
      
3. Create a report using the Splunk's `table` command to display the following fields in a statistics report:
    - `_time`
    - `IP_ADDRESS`
    - `DOWNLOAD_MEGABITS`
    - `UPLOAD_MEGABITS`
    - `ratio`
  
   Hint: Use the following format when for the `table` command: `| table fieldA  fieldB fieldC`

4. Answer the following questions:

`source="server_speedtest.csv" | eval ratio = 'UPLOAD_MEGABITS' / 'DOWNLOAD_MEGABITS' | table _time, IP_ADDRESS, DOWNLOAD_MEGABITS, UPLOAD_MEGABITS, ratio`

    - Based on the report created, what is the approximate date and time of the attack?
     - 2/23/2020
    - How long did it take your systems to recover?
     - 6 Hrs.

![Week 18-1](https://github.com/tajambois/Home-Work/blob/main/Week%2018/Screenshot/wk18-1.png)

Submit a screen shot of your report and the answer to the questions above.
 
### Step 2: Are We Vulnerable? 

**Task:** Create a report determining how many critical vulnerabilities exist on the customer data server. Then, build an alert to notify your team if a critical vulnerability reappears on this server.

1. Upload the following file from the Nessus vulnerability scan.
   - [Nessus Scan Results](resources/nessus_logs.csv)

2. Create a report that shows the `count` of critical vulnerabilities from the customer database server.
   - The database server IP is `10.11.36.23`.
   - The field that identifies the level of vulnerabilities is `severity`.
      
3. Build an alert that monitors every day to see if this server has any critical vulnerabilities. If a vulnerability exists, have an alert emailed to `soc@vandalay.com`.

`source="nessus_logs.csv" dest_ip="10.11.36.23" | stats count by severity`

Submit a screenshot of your report and a screenshot of proof that the alert has been created.

![Week18-2](https://github.com/tajambois/Home-Work/blob/main/Week%2018/Screenshot/wk18-2.png)

### Step 3: Drawing the (base)line

**Task:** Analyze administrator logs that document a brute force attack. Then, create a baseline of the ordinary amount of administrator bad logins and determine a threshold to indicate if a brute force attack is occurring.

1. Upload the administrator login logs.
   - [Admin Logins](resources/Administrator_logs.csv)

2. When did the brute force attack occur?
   - Hints:
     - Look for the `name` field to find failed logins.
     - Note the attack lasted several hours.

      
3. Determine a baseline of normal activity and a threshold that would alert if a brute force attack is occurring.

4. Design an alert to check the threshold every hour and email the SOC team at SOC@vandalay.com if triggered. 

Submit the answers to the questions about the brute force timing, baseline and threshold. Additionally, provide a screenshot as proof that the alert has been created.

![wk18-3](https://github.com/tajambois/Home-Work/blob/main/Week%2018/Screenshot/wk18-3.png)

![wk18-4](https://github.com/tajambois/Home-Work/blob/main/Week%2018/Screenshot/wk18-4.png)
 
 
### Your Submission
  
In a word document, provide the following:
  - Answers to all questions where indicated. 
  - Screenshots where indicated.

---

© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
