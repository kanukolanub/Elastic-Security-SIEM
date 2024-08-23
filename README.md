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

It will automatically start collecting and forwarding logs to your Elastic SIEM instance, although it might take a few minutes for the logs to appear in the SIEM.

Now in elastic website, it is displayed as agent enrolled. Click on "Add the Integration"
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
   Now that I have forwarded data from the Kali VM to the SIEM, I can start querying and analyzing the logs in the SIEM.

    In the search bar enter the below log query, process.args: "nmaps"

   ![image](https://github.com/user-attachments/assets/1e6b5068-a190-4510-8d30-b03667e08d40)

   click on view on any shown results to view the nmap encounter

   ![image](https://github.com/user-attachments/assets/616d6149-12b6-4ab9-86c7-ac04e8d1bc36)

   ![image](https://github.com/user-attachments/assets/8f1dbee1-5d2a-4c12-aa0f-156d629c56f8)

7. Create Dashboards to Visualize events
we can also utilize the visualizations and dashboards within the SIEM app to analyze logs and identify patterns or anomalies in the data. For instance, you could create a straightforward dashboard that displays a count of security events over time.

click on "dashboard" that is under analytics
![image](https://github.com/user-attachments/assets/19e188dc-1e57-49e9-9d51-76df1b0efde6)

click on "Create Dashboard"
![image](https://github.com/user-attachments/assets/66d9f453-2f76-4f69-a934-e716667e5ce0)

select on "Create Visualization"
![image](https://github.com/user-attachments/assets/01b7efb6-54b9-4b99-85c2-f339450a979a)

Select "Area" as the Visualization type, "Count" as the Vertical Field, and "Timestamp" for horizontal field
We see the graph below that shows the Nmap counts
![image](https://github.com/user-attachments/assets/6a40c976-5cf5-46e0-a73a-f4b3a039022f)

8. Create an alert
In a SIEM, alerts were a crucial feature for detecting security incidents and responding to them in a timely manner.
Alerts were created based on predefined rules or custom queries and could be configured to trigger specific actions when certain conditions were met.
In this task, I walked through the steps of creating an alert in the Elastic SIEM instance to detect Nmap scans.

click on Alerts
![image](https://github.com/user-attachments/assets/0230f83c-af17-4d40-9be6-06a828000018)

click on Manage rules
![image](https://github.com/user-attachments/assets/45a1e91b-7d83-491c-9998-6f6012d8b9ae)

click on Create rule
![image](https://github.com/user-attachments/assets/10a071f1-b167-4bcc-b5f1-5b3d56f69731)

select custom threshold
![image](https://github.com/user-attachments/assets/2d7337cf-5c93-4e86-960e-4bf349dcc4d0)





