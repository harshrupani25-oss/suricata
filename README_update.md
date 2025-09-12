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

(./images/overview.png)  


🧮 Requirements

Operating System: Ubuntu/Debian (recommended)  

CPU/RAM: Minimum 2 cores, 4 GB RAM  

Tools: `git`, `curl`, `wget`, `tcpdump`, `nmap`  

Network: One interface to monitor traffic  




🏗️ Installation

bash:-

    sudo apt update
    sudo apt install -y software-properties-common wget curl git


Add Suricata repository:-

    sudo add-apt-repository ppa:oisf/suricata-stable
    sudo apt update

Install Suricata:-

    sudo apt install -y suricata

🧑‍💻create a suricata rule for Network-based attacks in Nmap:-

    Nmap Stealth Scan Detection: Create a Suricata rule to detect TCP SYN packets sent to multiple ports within a short time frame, indicative of Nmap stealth scans.
    alert tcp any any -> any any (msg:"Nmap Stealth Scan Detected"; flags:S; threshold: type threshold, track by_src, count 5, seconds 10; sid:100001;)
