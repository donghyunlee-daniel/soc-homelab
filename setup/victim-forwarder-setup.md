\# Splunk Universal Forwarder Setup on Linux Victim



\## Objective

Configure a Linux endpoint to forward authentication logs to a central Splunk SIEM for SOC monitoring.



---



\## Environment



| Role | OS | Details |

|----|----|-------|

| SOC Server | Ubuntu Server | Splunk Enterprise |

| Victim | Ubuntu Desktop | OpenSSH enabled |

| Network | Internal Network | Log forwarding |



---



\## Architecture Overview

\- Victim forwards logs via Internal Network

\- Splunk Web accessed via Host-only interface



(Insert network diagram here)



---



\## Installation



Downloaded Splunk Universal Forwarder for Linux (amd64):



```bash

wget https://download.splunk.com/...linux-amd64.deb

sudo dpkg -i splunkforwarder-linux-amd64.deb



