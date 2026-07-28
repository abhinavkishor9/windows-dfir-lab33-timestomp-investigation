# windows-dfir-lab33-timestomp-investigation
## Overview

Windows stores multiple timestamps for every file that provide investigators with valuable forensic evidence. Attackers often manipulate these timestamps to conceal malicious activity, making files appear older or consistent with legitimate system activity. This anti-forensics technique is known as **Time Stomping**.

In this investigation, a controlled environment was created to simulate timestamp manipulation using native Windows PowerShell commands. The investigation focused on identifying modified timestamps, comparing original and altered metadata, and understanding the forensic significance of timestamp inconsistencies.

---

# Executive Summary

This investigation demonstrates one of the most common anti-forensics techniques observed during DFIR engagements: **Time Stomping**. A sample document was intentionally modified so that its Creation Time, Last Write Time, and Last Access Time appeared several years older than its actual creation date. The altered timestamps were then validated using both PowerShell and Windows File Properties.

The exercise illustrates how investigators identify suspicious timestamp anomalies and why timestamp analysis alone should never be treated as conclusive evidence without corroborating additional forensic artifacts.

---

# Investigation Objectives

- Understand Windows file timestamps.
- Learn the concept of Time Stomping.
- Modify timestamps using PowerShell.
- Identify manipulated timestamps.
- Correlate timestamp evidence.
- Document forensic findings.

---

# Skills Demonstrated

- Windows DFIR
- Anti-Forensics Detection
- Windows File System Analysis
- PowerShell Investigation
- Evidence Preservation
- Timestamp Analysis
- File Metadata Validation
- Evidence Correlation
- Incident Documentation

---

# Lab Environment

| Component | Details |
|----------|---------|
| Operating System | Windows 10 x64 |
| Platform | VMware Workstation Player |
| Tools Used | PowerShell, File Explorer, File Properties |

---

# MITRE ATT&CK Mapping

| Technique | ID |
|-----------|----|
| Indicator Removal: Time Stomp | T1070.006 |

---

# Investigation Scenario

During a routine DFIR investigation, analysts discovered a document whose timestamps appeared significantly older than surrounding files within the same directory. Such inconsistencies may indicate an attempt to disguise recently created artifacts as legitimate historical files.

The objective of this investigation was to reproduce this behavior in a controlled environment, identify manipulated timestamps, and understand how timestamp anomalies can support forensic investigations.

---

# Investigation Steps

1. Created the investigation workspace.
2. Generated sample files.
3. Recorded original timestamps.
4. Modified timestamps using PowerShell.
5. Verified modified timestamps.
6. Compared PowerShell output with File Properties.
7. Identified timestamp anomalies.
8. Correlated collected evidence.
9. Documented investigation findings.
10. Cleaned up the lab.

---

# Evidence Collected

- Investigation folder
- Sample files
- Original timestamps
- Modified timestamps
- PowerShell outputs
- File Properties screenshots
- Cleanup verification

---

# Evidence Correlation

The investigation correlated multiple evidence sources to validate timestamp manipulation:

- Original PowerShell timestamp output
- Modified PowerShell timestamp output
- Windows File Properties
- Sample file creation timeline
- Timestamp modification commands

Correlation confirmed that only the selected document had altered timestamps while the remaining files retained their original values.

---

# Investigation Findings

The investigation confirmed that:

- Windows file timestamps can be modified using native PowerShell.
- Timestamp manipulation affects visible metadata presented to investigators.
- Altered timestamps may falsely indicate that a file existed much earlier than its actual creation.
- Timestamp analysis should always be correlated with additional forensic artifacts before drawing investigative conclusions.

---

# Key Takeaway

Time Stomping is a common anti-forensics technique that attempts to mislead investigators by modifying file timestamps. Effective DFIR investigations require correlating timestamp evidence with other forensic artifacts to accurately reconstruct system activity and identify attempts to conceal malicious behavior.

---

