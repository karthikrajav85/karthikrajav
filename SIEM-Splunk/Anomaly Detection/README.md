# Authentication Anomaly Detection using Splunk (BOTS v3)

## Project Overview

In this project, I used Splunk Enterprise and BOTS v3 dataset to analyze authentication logs and identify unusual login behavior.

The main goal of this project is to understand how login activities happen in a system and detect any abnormal patterns which may indicate a security issue.

---

## Objective

* Load real-world log data into Splunk
* Analyze authentication events (Windows Security logs)
* Identify normal vs abnormal user behavior
* Detect suspicious login patterns

---

## Tools Used

* Splunk Enterprise
* BOTS v3 Dataset
* SPL (Search Processing Language)

---

## Dataset

* BOTS v3 dataset (Splunk Boss of the SOC)
* Contains multiple log sources like:

  * Windows Event Logs
  * Network logs
  * DNS, Syslog, etc.

---

## Step-by-Step Approach

### 1️⃣ Data Ingestion

* Uploaded BOTS v3 dataset into Splunk
* Created index: `botsv3`
* Verified data using:

```
index=botsv3
```

---

### 2️⃣ Understanding the Data

* Identified different sourcetypes:

```
index=botsv3 | stats count by sourcetype
```

* Focused on:

```
WinEventLog:Security
```

---

### 3️⃣ Filtering Authentication Logs

* Analyzed successful login events:

```
index=botsv3 sourcetype="WinEventLog:Security" EventCode=4624
| stats count by Account_Name
| sort -count
```

---

### 4️⃣ Identifying Real Users

* Removed system and machine accounts
* Focused on human users like:

```
bstoll@froth.ly
```

---

### 5️⃣ User Activity Investigation

* Investigated specific user activity:

```
index=botsv3 sourcetype="WinEventLog:Security" Account_Name="bstoll@froth.ly"
| table _time, ComputerName, Logon_Type
| sort _time
```

---

### 6️⃣ Time-Based Analysis

* Checked login pattern over time:

```
index=botsv3 sourcetype="WinEventLog:Security" Account_Name="bstoll@froth.ly"
| timechart count
```

---

### 7️⃣ Anomaly Detection

* Detected multiple logins in same second:

```
index=botsv3 sourcetype="WinEventLog:Security" Account_Name="bstoll@froth.ly"
| stats count by _time
| where count > 1
```

---

## Key Findings

* Most login activity was from SYSTEM and machine accounts (normal behavior)
* Identified a real user: **[bstoll@froth.ly](mailto:bstoll@froth.ly)**
* Found multiple login events happening within the same second
* Login activity repeated within a short time window
* Logon types observed: 7 (Unlock), 11 (Cached login)

---

## Security Insight

This behavior is not typical for a normal user.

Possible reasons:

* Automated login activity
* Script-based authentication
* Session reuse or background process

This indicates an **authentication anomaly**, not a brute force attack.

---

## Visualization

* Created time-based chart to clearly show login spikes
* Helps to easily identify abnormal behavior

---

## What I Learned

* How to load and explore large datasets in Splunk
* How to identify correct sourcetype and fields
* How to filter noise (system accounts)
* How to analyze user behavior
* How to detect anomalies using time-based analysis

---

## Conclusion

In this project, I successfully analyzed authentication logs and identified abnormal login behavior using Splunk.

Even though there was no brute force attack, I was able to detect suspicious patterns which could indicate automated or unusual activity.

This project helped me understand real-world SOC analysis and how to investigate security events effectively.

---

## Project Screenshots

* Data Ingestion
* Sourcetype Analysis
* Login Analysis
* User Investigation
* Time Analysis
* Anomaly Detection
* Visualization

---

---

