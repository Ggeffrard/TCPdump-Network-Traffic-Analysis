# TCPdump-Network-Traffic-Analysis

## Project Overview

In this project, I used TCPdump to capture and analyze network traffic within a Linux environment. I identified active network interfaces, applied packet filters, captured live network traffic, and reviewed packet data to gain insight into network communications. This project demonstrates practical experience with network monitoring, packet analysis, and command-line tools commonly used in cybersecurity investigations and incident response activities.

## Skills Demonstrated

Network Traffic Analysis
Packet Capture and Inspection
TCPdump Usage
Linux Command Line Operations
Network Interface Identification
Packet Filtering
Incident Response Fundamentals
Cybersecurity Investigation


## Tools Used

TCPdump
Linux Terminal
Linux Virtual Machine


# Identify Network Interface

The purpose of this task was to identify the network interfaces available on the Linux system and determine which interface would be used for packet capture during the investigation.

Step 1: Used the ifconfig command to view the available network interfaces and identify the active interface:

sudo ifconfig

<img width="783" height="412" alt="Screenshot 2026-06-11 095255" src="https://github.com/user-attachments/assets/623bc71e-d2be-4241-b805-92aa2b18f26a" />

Used the tcpdump -D command to display the interfaces available for packet capture and verify the interface selected for the lab:

sudo tcpdump -D

<img width="751" height="288" alt="Screenshot 2026-06-11 095329" src="https://github.com/user-attachments/assets/182181c9-d96f-4eee-8a91-287c251ebf5a" />

# Inspect Network Traffic with TCPdump

Used TCPdump on the eth0 interface to capture and inspect live network traffic. Reviewed packet details returned by the command to observe network communications and analyze traffic activity.

Filter live network packet data from the eth0 interface with tcpdump:

sudo tcpdump -i eth0 -v -c5

<img width="1900" height="458" alt="Screenshot 2026-06-11 100740" src="https://github.com/user-attachments/assets/dfa5721a-a6f2-4eee-8eb1-ee0cf6fa6aee" />

# Capture Network Traffic with TCPdump

The purpose of this task was to capture network traffic and save the packet data to a packet capture file for further analysis. A TCPdump filter was applied to collect web traffic (TCP port 80), and the captured data was stored in a .pcap file.

Step 1. Used TCPdump to capture TCP port 80 traffic on the eth0 interface and save the results to a file named capture.pcap.

Run this command line:

sudo tcpdump -i eth0 -nn -c9 port 80 -w capture.pcap &

<img width="1230" height="92" alt="Screenshot 2026-06-11 100926" src="https://github.com/user-attachments/assets/5701c4f3-0884-4a5d-b929-1253623f18ae" />

Step 2. Generated web traffic using the curl command to create network activity for capture.

Run this command line:

curl opensource.google.com

<img width="947" height="257" alt="Screenshot 2026-06-11 101157" src="https://github.com/user-attachments/assets/6dab431a-ab73-480d-8cce-27c0f75f3496" />

Step 3. Verified that the packet capture file was successfully created and contained the captured traffic.

Run this command line:

ls -l capture.pcap

<img width="987" height="92" alt="Screenshot 2026-06-11 101228" src="https://github.com/user-attachments/assets/83ecd526-0820-4b78-9def-cd712bff9dcd" />

# Filter Captured Packet Data

The purpose of this task was to analyze the contents of the packet capture file by applying TCPdump filters and reviewing detailed packet information. This allowed for a closer examination of network traffic and packet data stored in the capture file.

Step 1. Used TCPdump to read and display detailed packet header information from the capture.pcap file.

Run this command line: 

sudo tcpdump -nn -r capture.pcap -v

<img width="1896" height="963" alt="Screenshot 2026-06-11 102048" src="https://github.com/user-attachments/assets/c77d21d6-cf38-4333-aa40-22224df1eaba" />
<img width="1891" height="127" alt="Screenshot 2026-06-11 102111" src="https://github.com/user-attachments/assets/11d626ed-1680-4128-a3ea-d85031aca974" />

Step 2. Used TCPdump to examine the packet data in hexadecimal and ASCII format for deeper traffic analysis.

Run this command: 

sudo tcpdump -nn -r capture.pcap -X

<img width="1897" height="967" alt="Screenshot 2026-06-11 102356" src="https://github.com/user-attachments/assets/a8764455-9307-4548-87d6-37bfd047f2a9" />
<img width="1808" height="965" alt="Screenshot 2026-06-11 102422" src="https://github.com/user-attachments/assets/cfa5cc19-686b-4dcf-a558-fc9b1cf593f4" />
<img width="1741" height="95" alt="Screenshot 2026-06-11 102444" src="https://github.com/user-attachments/assets/ce2f4b40-da42-4166-8e0e-13b0327a3f08" />

# Findings

- Successfully captured and analyzed network traffic using TCPdump.
- Identified active network interfaces and monitored their activity.
- Applied packet filters to isolate specific network communications.
- Improved understanding of network protocols and packet structures.
- Gained hands-on experience with packet analysis techniques used during cybersecurity investigations.


# Conclusion

This project provided practical experience using TCPdump to monitor and analyze network traffic in a Linux environment. By capturing packets, filtering network activity, and reviewing traffic patterns, I strengthened my understanding of network communications and packet analysis. The skills developed through this project are directly applicable to incident response, threat detection, and network security monitoring within cybersecurity operations.







