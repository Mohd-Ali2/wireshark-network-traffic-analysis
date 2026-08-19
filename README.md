# Wireshark Network Traffic Investigation

This project is a small network traffic investigation lab built around a real PCAP from Malware-Traffic-Analysis.net.

I used Wireshark to work through the capture and understand what was happening on the network instead of relying on a prepared answer. The main focus was identifying the affected host, following its traffic, finding unusual connections, and extracting useful indicators from the capture.

## PCAP

**Exercise:** 2022-03-21 - Traffic Analysis Exercise - Infection from a Word Document

**Source:**
https://www.malware-traffic-analysis.net/2022/03/21/index.html

**Tool:** Wireshark

The capture contains normal internal traffic as well as activity that needs further investigation. The main internal host examined during the investigation was `10.0.19.14`.

## What I Investigated

The investigation mainly focused on:

* Identifying the likely affected endpoint
* Using DHCP traffic to understand the host
* Looking at Kerberos traffic to identify the user
* Reviewing DNS activity
* Investigating HTTP traffic
* Checking conversations and external destinations
* Looking at unusual outbound connections
* Building a basic timeline from the available traffic
* Extracting relevant indicators of compromise

One of the connections that required further investigation was traffic from `10.0.19.14` to `23.227.198.203` over TCP port `757`.

## Investigation Process

The project follows a simple workflow:

```text
PCAP
  ↓
Identify Hosts
  ↓
Filter Traffic
  ↓
Follow Conversations
  ↓
Find Unusual Activity
  ↓
Extract IOCs
  ↓
Build Timeline
  ↓
Write Findings
```

I used Wireshark features such as display filters, Endpoints, Conversations, packet details, and protocol-specific analysis to narrow down the relevant traffic.

## Project Structure

```text
Wireshark-network-traffic-analysis/

├── investigation/
│   ├── incident-report.md
│   └── notes.md
│
├── screenshots/
│
├── pcap/
│
└── README.md
```

The `investigation` directory contains the final investigation report and working notes. Screenshots contain the evidence collected during the analysis.

## What I Learned

This project helped me get more comfortable with reading network traffic and understanding what normal and unusual communication can look like in a packet capture.

The main areas I worked with were:

* TCP/IP traffic
* DHCP
* DNS
* HTTP
* Kerberos
* TCP conversations
* Source and destination analysis
* IOC identification
* Basic network incident investigation

## Conclusion

The purpose of this project was not to become an expert in every Wireshark feature. It was to practice approaching a PCAP like a SOC analyst: start with the available evidence, identify the important host and connections, investigate the traffic, and build a conclusion from what can actually be observed.

## References

Malware-Traffic-Analysis.net
https://www.malware-traffic-analysis.net/2022/03/21/index.html

Wireshark
https://www.wireshark.org/
