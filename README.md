# Nmap-Suricata-Splunk

# Detecting and Visualizing Nmap Scans Using Suricata and Splunk

## Objective
This project simulated a real-world network intrusion detection and monitoring scenario. The primary goal was to detect Nmap SYN scan activity (reconnaissance) using Suricata and visualize the resulting alert patterns through Splunk.

## Skills Learned
- Configuring IDS tools (Suricata) for real-time network traffic monitoring
- Writing custom Suricata detection rules
- Simulating reconnaissance attacks (Nmap SYN scans)
- Forwarding and analyzing IDS logs using Splunk Universal Forwarder
- Building detection logic and threat visualization in SIEM platforms

## Tools Used
- Suricata (Intrusion Detection System)
- Splunk Universal Forwarder + Splunk Server
- Kali Linux (Attacker Machine)
- Ubuntu (Victim Machine)

## Lab Setup

| Virtual Machine | Role                              | IP Address     |
|------------------|-----------------------------------|----------------|
| Ubuntu VM        | Victim Machine running Suricata   | 192.168.1.30   |
| Kali Linux VM    | Attacker Machine (Nmap scanning)  | 192.168.1.59   |
| Splunk Server    | Receives and visualizes alerts    | 192.168.1.200  |

## Steps Taken

1. **Installed Suricata** on the Ubuntu victim machine.
2. **Configured Suricata** by setting `HOME_NET` to the lab network (`192.168.1.0/24`).
3. **Created a custom Suricata rule** to detect 5 SYN Packets in 10 seconds.
4. **Launched an Nmap SYN scan** from Kali Linux(`nmap -sS`)
5. **Forwarded Suricata alerts** to Splunk.
6. **Queried and visualized the alerts in Splunk.**

## Custom Rule
   ```plaintext
   alert tcp any any -> any any (msg:"[ALERT] Nmap SYN Scan Detected"; flags:S; threshold:type threshold, track by_src, count 5, seconds 10; sid:1000002; rev:1;)
   ```

## Splunk Query
   ```plaintext
   Suricata:Fast
   index='main'
   ```

 
 
 ## Key Findings
- Successfully detected and logged SYN scan activities in Suricata.
- Forwarded and visualized Suricata logs into Splunk in real-time.
- Visualized scan attempts using Splunk dashboards and queries.
- Demonstrated how early detection of reconnaissance activities supports proactive SOC operations.

## Report
[Download full PDF report](https://drive.google.com/file/d/1XiJAaXAfUFfUiTmZJUyEsPU3QRX8MzHc/view?usp=drive_link)






## Screenshots

![Screenshot 2025-04-02 152256](https://github.com/user-attachments/assets/805add9a-0195-4c55-be3d-f36dabee259e)


![Screenshot 2025-04-02 152319](https://github.com/user-attachments/assets/23176c4c-1cb0-4255-add9-89f838aa676d)


![Screenshot 2025-04-02 152428](https://github.com/user-attachments/assets/fede1c6b-d7df-4ab3-a655-586756450d4b)


![Screenshot 2025-04-02 152841](https://github.com/user-attachments/assets/6b46395f-91ce-4d2e-a59b-7389946ea5c6)


![Screenshot 2025-04-02 153029](https://github.com/user-attachments/assets/8445b8b4-449d-48fd-88b0-7ad4b6e2f6fb)


![Screenshot 2025-04-02 161214](https://github.com/user-attachments/assets/cbd0196d-03a4-4e2d-b05d-a5d3aba542f2)


![Screenshot 2025-04-02 180338](https://github.com/user-attachments/assets/0c788c39-27fa-4d12-8c93-7486fb9eb57f)


![Screenshot 2025-04-02 180513](https://github.com/user-attachments/assets/15fd3ef2-80bb-49a8-87c2-75c7e299893c)


![Screenshot 2025-04-04 164919](https://github.com/user-attachments/assets/1a2a5dde-917e-463a-a3ef-faaefc0ebd46)


![Screenshot 2025-04-06 112845](https://github.com/user-attachments/assets/f69f834c-3d1c-4e7f-8fad-44cc8890e3ea)


![Screenshot 2025-04-06 112924](https://github.com/user-attachments/assets/937ad7ee-ab24-4eb9-b1a1-b8bc296b3e1d)



![Screenshot 2025-04-06 132633](https://github.com/user-attachments/assets/38054ad0-f08d-4b5e-b85b-3d8cdd05f1ab)



![Screenshot 2025-04-06 132648](https://github.com/user-attachments/assets/ffffe6d5-95bd-4007-9309-a5cc6fcbc689)
