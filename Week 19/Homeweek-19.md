### Part 1: Windows Server Attack

Note: This is a public-facing windows server that VSI employees access.
 
#### Question 1
- Several users were impacted during the attack on March 25th.
- Based on the attack signatures, what mitigations would you recommend to protect each user account? Provide global mitigations that the whole company can use and individual mitigations that are specific to each user.
  - Due to the high volume of pressure on password bruting, it would be this anaylst recommendation for education to employee about password strength and indiviudailty. Having cergtain length and special charaters are a must. Not repeating the same password across platforms and services is also crutial.
  
#### Question 2
- VSI has insider information that JobeCorp attempted to target users by sending "Bad Logins" to lock out every user.
- What sort of mitigation could you use to protect against this?
  - Creating an alert that would notify staff after 21 bad log on attempts were detected. After baslining this action for normal behavior, this threshold will notify and better prepare SOC for action.
  

### Part 2: Apache Webserver Attack:

#### Question 1
- Based on the geographic map, recommend a firewall rule that the networking team should implement.
- Provide a "plain english" description of the rule.
  - Block all incoming POST requests when coming from source IP address from Kyiv, Ukraine.

- Provide a screen shot of the geographic map that justifies why you created this rule. 

![wk19-1](https://github.com/tajambois/Home-Work/blob/main/Week%2019/screenshot/wk-19.png)
  
#### Question 2

- VSI has insider information that JobeCorp will launch the same webserver attack but use a different IP each time in order to avoid being stopped by the rule you just created.

- What other rules can you create to protect VSI from attacks against your webserver?
  - Conceive of two more rules in "plain english". 
  - Hint: Look for other fields that indicate the attacker.
  


### Guidelines for your Submission:
  
In a word document, provide the following:
- Answers for all questions.
- Screenshots where indicated

Submit your findings in BootCampSpot!
