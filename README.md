# SOC Homelab – Splunk SIEM

This repository documents a SOC homelab built to practice centralized log collection, detection, and basic incident investigation using Splunk.

The lab is designed to simulate realistic attack and monitoring scenarios in an isolated environment.

---

## Lab Components

- **Splunk Enterprise** – SOC server for log ingestion and analysis  
- **Linux Victim** – Ubuntu system forwarding logs via Splunk Universal Forwarder  
- **Kali Linux** – attacker machine used to generate test activity  
- **Internal Network** – isolates lab traffic from the host and external internet

---

## Current Status

- Splunk Enterprise installed and running  
- Universal Forwarder configured on victim machine  
- Authentication logs successfully ingested into Splunk  
- SSH access enabled for controlled attack testing

---

## Scenarios 

- SSH brute-force detection  
- Failed vs successful login analysis  
- Source IP behavior review
- Port scan detection  
- Suspicious authentication patterns  
- Basic network traffic analysis and correlation  

Scenarios are added incrementally as the lab evolves.

---

## Repository Structure

- `setup/` – installation and configuration steps  
- `scenarios/` – individual attack and detection writeups  
- `architecture/` – lab topology and network layout  
- `docs/` – notes, observations, and lessons learned

---

## Purpose

This lab is used to build practical SOC skills, focusing on log visibility, detection logic, and clear documentation of findings.
