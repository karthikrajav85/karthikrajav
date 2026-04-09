# Network Behavior Analysis using Splunk (BOTS v3)

---

## Executive Summary

This project analyzes network traffic logs using Splunk to understand normal and abnormal network behavior. The analysis identified unusual outbound communication, traffic spikes, and rare network activities that may indicate potential security risks.

---

## Project Overview

In this project, I used Splunk Enterprise with the BOTS v3 dataset to analyze network logs and detect abnormal patterns in network traffic.

The focus is on identifying:

* Traffic behavior
* External communication
* Anomalies in ports and DNS

---

## Objective

* Analyze network traffic logs
* Understand normal traffic behavior
* Identify top communicating systems
* Detect external communication
* Identify anomalies in traffic, ports, and DNS

---

## Tools Used

* Splunk Enterprise
* BOTS v3 Dataset
* SPL (Search Processing Language)

---

## Step-by-Step Approach

---

### 1. Data Validation

```spl
index=botsv3
```

Verified that data is properly ingested and searchable in Splunk.

---

### 2. Sourcetype Analysis

```spl
index=botsv3 | stats count by sourcetype
```

Identified different log sources and confirmed availability of network-related logs.

---

### 3. Network Log Identification

```spl
index=botsv3 sourcetype=stream:*
```

Filtered and focused only on network traffic logs for analysis.

---

### 4. Baseline Traffic Analysis

```spl
index=botsv3 sourcetype=stream:*
| timechart span=1h count
```

Understood normal traffic patterns over time to establish a baseline.

---

### 5. Top Talkers (Source IPs)

```spl
index=botsv3 sourcetype=stream:*
| stats count by src_ip
| sort -count
```

Identified systems generating the most network traffic.

---

### 6. Top Destinations

```spl
index=botsv3 sourcetype=stream:*
| stats count by dest_ip
| sort -count
```

Analyzed which destinations receive the most traffic.

---

### 7. External Communication

```spl
index=botsv3 sourcetype=stream:*
| where NOT (cidrmatch("172.16.0.0/12", dest_ip) OR cidrmatch("192.168.0.0/16", dest_ip))
```

Filtered internal traffic to focus only on communication with external systems.

---

### 8. High External Traffic

```spl
index=botsv3 sourcetype=stream:*
| where NOT (cidrmatch("172.16.0.0/12", dest_ip) OR cidrmatch("192.168.0.0/16", dest_ip))
| stats sum(bytes_out) as total_outbound by src_ip, dest_ip
| sort -total_outbound
```

Identified systems sending large amounts of data to external IPs.

---

### 9. Time-Based Analysis

```spl
index=botsv3 sourcetype=stream:*
| timechart span=1h count
```

Detected unusual spikes in traffic over time.

---

### 10. Port Analysis

```spl
index=botsv3 sourcetype=stream:*
| stats count by dest_port
| sort -count
```

Analyzed commonly used destination ports.

---

### 11. Rare Port Analysis

```spl
index=botsv3 sourcetype=stream:*
| stats count by dest_port
| where count < 50
| sort count
```

Identified rarely used ports which may indicate suspicious activity.

---

### 12. DNS Analysis

```spl
index=botsv3 sourcetype=stream:dns
| stats count by query
| sort -count
```

Analyzed frequently accessed domains.

---

### 13. Rare DNS Queries

```spl
index=botsv3 sourcetype=stream:dns
| stats count by query
| where count < 5
| sort count
```

Identified low-frequency DNS queries for anomaly detection.

---

## Business Impact

The identified network behavior can have the following impact on the organization:

* **Data Leakage**: Sensitive data may be transferred outside the organization without authorization
* **Loss of Confidential Information**: Business-critical or customer data could be exposed
* **Regulatory Risk**: Violations of data protection laws (GDPR, etc.)
* **Financial Loss**: Potential fines, legal costs, or business disruption
* **Reputation Damage**: Loss of customer trust and brand value

---

## Risk Assessment

| Factor           | Assessment                                                     |
| ---------------- | -------------------------------------------------------------- |
| **Threat**       | Unauthorized data transfer / suspicious outbound communication |
| **Likelihood**   | Medium to High                                                 |
| **Impact**       | High                                                           |
| **Overall Risk** | **High**                                                       |

---

## Risk Explanation

* Systems are communicating with **external IP addresses**
* **High outbound traffic** observed from specific hosts
* **Traffic spikes** indicate abnormal behavior
* Presence of **rare ports and DNS queries** suggests potential anomalies

These indicators increase the probability of:

* Data exfiltration
* Malware communication
* Unauthorized network activity

---

## Key Findings

* Identified top communicating systems (source and destination)
* Observed significant external communication
* Detected high outbound traffic from specific systems
* Found traffic spikes indicating abnormal behavior
* Identified rare ports and DNS queries as anomalies

---

## Security Insight

The analysis shows patterns that may indicate:

* Unusual external communication
* Abnormal data transfer behavior
* Potential early signs of security threats

---

## What I Learned

* How to analyze network logs in Splunk
* How to establish baseline behavior
* How to detect anomalies in traffic
* How to identify suspicious network patterns

---

## Conclusion

This project demonstrates how network behavior analysis can be used to identify abnormal activity using Splunk. By analyzing traffic patterns, ports, and DNS queries, it is possible to detect potential security risks in a network environment.

---

## Project Screenshots

---

### 1. Data Validation

![Data Validation](screenshots/01_Data_Validation.png)

---

### 2. Sourcetype Analysis

![Sourcetype Analysis](screenshots/02_Sourcetype_Analysis.png)

---

### 3. Network Log Identification

![Network Logs](screenshots/03_Network_Log_Identification.png)

---

### 4. Baseline Traffic Trend

![Baseline Traffic](screenshots/04_Baseline_Traffic_Trend.png)

---

### 5. Top Talkers

![Top Talkers](screenshots/05_Top_Talkers.png)

---

### 6. Top Destinations

![Top Destinations](screenshots/06_Top_Destinations.png)

---

### 7. External Communication

![External Communication](screenshots/07_External_Communication.png)

---

### 8. High External Traffic

![High External Traffic](screenshots/08_High_External_Traffic.png)

---

### 9. Time-Based Analysis

![Time Analysis 1](screenshots/09_Time_Based_Analysis%20\(1\).png)

![Time Analysis 2](screenshots/09_Time_Based_Analysis%20\(2\).png)

---

### 10. Port Analysis

![Port Analysis](screenshots/10_Port_Analysis.png)

---

### 11. Rare Port Analysis

![Rare Ports](screenshots/11_Rare_Port_Analysis.png)

---

### 12. DNS Analysis

![DNS Analysis](screenshots/12_DNS_Analysis.png)

---

### 13. Rare DNS Queries

![Rare DNS](screenshots/13_Rare_DNS_Queries.png)

---



---

