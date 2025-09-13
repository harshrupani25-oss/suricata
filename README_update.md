🛡️ Suricata Home Lab


This repository contains the setup and configuration for a Suricata IDS/IPS Home Lab. The goal is to gain practical experience in deploying, configuring, and testing an Intrusion Detection System (IDS) for network security monitoring.


In this home-lab, we will cover:

📖 Overview

🖼️ Lab Diagram 

🧮 Requirements

🏗️ Installation

🧑‍💻 Create a suricata rule for Network-based attacks in Nmap



📖 Overview

The goal of setting up a Suricata home-lab is to gain practical experience in deploying and configuring an Intrusion Detection System (IDS) for network security monitoring. Suricata is an open-source IDS capable of detecting and preventing various network-based threats. This home-lab provides individuals with hands-on experience in setting up, configuring, and utilizing Suricata to enhance network security.

🖼️Lab Diagram

<img width="1536" height="1024" alt="suricata home lad diagram" src="https://github.com/user-attachments/assets/1ecaf11c-58bd-4c94-9e2f-c30a4078a466" />


Architecture Diagram


<img width="2000" height="1414" alt="suricata architecture" src="https://github.com/user-attachments/assets/026622cc-785b-4e4c-a989-a548a4e1f26f" />




🧮 Requirements

Operating System: Ubuntu/Debian (recommended)  

CPU/RAM: Minimum 2 cores, 4 GB RAM  

Tools: `git`, `curl`, `wget`, `tcpdump`, `nmap`  

Network: One interface to monitor traffic  




🏗️ Installation

bash:-

    sudo apt update && sudo apt upgrade -y
    sudo apt install suricata -y
    suricata --build-info
    wget -O suricata.tar.gz "https://www.openinfosecfoundation.org/download/suricata-8.0.0.tar.gz"


Add Suricata repository:-

    sudo add-apt-repository ppa:oisf/suricata-stable
    sudo apt update

🧑‍💻create a suricata rule for Network-based attacks in Nmap:-

    Nmap Stealth Scan Detection: Create a Suricata rule to detect TCP SYN packets sent to multiple ports within a short time frame, indicative of Nmap stealth scans.
    alert tcp any any -> any any (msg:"Nmap Stealth Scan Detected"; flags:S; threshold: type threshold, track by_src, count 5, seconds 10; sid:100001;)
