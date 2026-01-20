# SSH Root Account Brute Force Detection

## Scenario Overview
This scenario demonstrates the detection of an SSH brute-force attack targeting root account in a controlled SOC homelab environment.
The goal is to practice identifying suspicious authentication behavior using log analysis and time-based detection logic in Splunk.


## Lab Environment
This scenario was executed using the existing SOC homelab environment described in the root README, consisting of a Splunk SIEM, Ubuntu victim, and Kali attacker within an isolated internal network.



## Attack Simulation
The attacker system (Kali Linux) attempted multiple SSH logins against the root account of victim machine using incorrect credentials.
A total of 6 failed login attempts were generated, followed by 1 successful login.
All attack activity was performed within an isolated internal network environment.


## Log Analysis
SSH authentication logs were collected from the victim system and analyzed in Splunk.

Key fields used in this analysis:
- src_ip: Source IP address of the SSH login attempts
- failed_attempts: Number of failed SSH authentication attempts
- successful_logins: Number of successful SSH logins
- duration: Time window between the first and last login attempt


## Detection Logic
This scenario uses the following detection rule:

- `detection/ssh_bruteforce.spl`
- `detection/ssh_bruteforce_time_window.spl`

This detection identifies multiple failed SSH authentication attempts (e.g. >= 5 failures) from a single source IP followed by a successful login within a short time window (e.g. 5 minutes).
The goal is to detect potential SSH brute-force activity that results in account compromise.

## Screenshots
![Failed vs Success](screenshots/splunk_root_ssh_failed_vs_success.png)
![Time Window Detection](screenshots/splunk_root_ssh_time_window.png)

## Lessons Learned
- Manual SSH login attempts help distinguish normal user behavior from automated brute-force attacks.
- Time-based thresholds are critical for reducing false positives in authentication monitoring.
- Preserving raw logs while selectively using relevant fields is essential for effective SOC analysis.
- Documenting detection logic improves repeatability and investigation consistency.
- Successful authentication following repeated failures significantly increases the confidence of a true positive alert.
