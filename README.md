# Elastic-SIEM

## Overview

This repository contains an overview of how to use Elastic Security a security solution built on the Elastic Search platform offered by Elastic to detect alerts generated when an adversary conducts a nmap scan on Kali Linux (Ubuntu OS).

1. Install Elastic Search Platform v8.15
   ![image](https://github.com/user-attachments/assets/2d6f016a-6003-4bac-86a9-aebf8216a320)

2. Then integrate Elastic Defend (comprehensive security solution designed to protect hosts and cloud workloads. It offers prevention, detection and response capabilities) with Elastic Search Platform v8.15.
   ![image](https://github.com/user-attachments/assets/90f4c0c0-3333-4ddd-96b5-6bedd3871142)

3. We shall install Elastic Agent (a unified tool designed to simplify the collection and monitoring of various data types from your systems.
   It can gather logs, metrics, traces, availability, security data, and more from each host) on Kali Linux (Ubuntu OS) in VM Virtual Box.
   ![image](https://github.com/user-attachments/assets/75c82d8f-7bcf-4e28-926a-04d0dc88b912)

   ![image](https://github.com/user-attachments/assets/1d580745-e819-4d8a-bf85-a82302e95636)

   ![image](https://github.com/user-attachments/assets/f72be1ca-e253-4619-977e-627b15dbe744)

4. You can confirm whether the Elastic Agent has been installed correctly by running the following command
   sudo systemctl status elastic-agent.service
   ![image](https://github.com/user-attachments/assets/b4262002-5257-480e-9588-25b1e833a7c7)

5. Generating Security Events on Kali Linux (Ubuntun OS) VM.
   To verify that the agent was working correctly, I generated some security-related events on my Kali VM using a tool like Nmap.
   Nmap (Network Mapper) is a free and open-source utility used for network exploration, management, and security auditing.
   It was designed to discover hosts and services on a computer network, thus creating a "map" of the network.
   Nmap was used to scan hosts for open ports, determine the operating system and software running on the target system, and gather other information about the network.

**nmap -p- localhost**

![image](https://github.com/user-attachments/assets/2d8d6c4b-21b7-4926-abb4-13b5616aa248)

**nmap -Ss localhost**
![image](https://github.com/user-attachments/assets/29fd33ca-5e1d-4d17-b7e0-a397b4b31c99)

6. Let's search for Security events in Elastic SIEM
