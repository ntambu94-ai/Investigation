# #SIEM-Brute-Force-Investigation

# Incident Investigation: Brute Force Login Attack

## Scenario

Multiple failed login attempts were detected on a Windows endpoint.

This behavior may indicate a brute force authentication attack.

---

## Detection Method

Windows Security Event Logs

Event ID: 4625 (Failed Logon)

---

## SIEM Query

SecurityEvent
| where EventID == 4625
| summarize FailedAttempts=count() by Account, IPAddress
| where FailedAttempts > 10

---

## Investigation Steps

1. Identified repeated failed login attempts
2. Determined source IP address
3. Checked login pattern frequency
4. Reviewed targeted user accounts

---

## Findings

• More than 15 failed login attempts detected  
• Source IP identified as attacker machine  
• Attack pattern consistent with brute force authentication attempt  

---

## Analyst Response

• Investigated affected account  
• Recommended account lockout policy  
• Suggested monitoring repeated login failures  

---

## Lessons Learned

Monitoring failed login attempts helps detect brute force attacks early.
