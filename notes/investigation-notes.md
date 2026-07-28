# Investigation Notes

## Lab Summary

**Objective:**

Investigate Windows Time Stomping by modifying file timestamps using PowerShell, identifying timestamp inconsistencies, validating evidence, and documenting anti-forensics indicators.

---

## Analyst Methodology

The investigation followed a standard host-based DFIR methodology:

1. Prepare a controlled investigation environment.
2. Generate sample files.
3. Record original timestamps.
4. Perform timestamp manipulation.
5. Validate modified timestamps.
6. Correlate collected evidence.
7. Document investigation findings.
8. Produce an investigation timeline.

---

## Investigation Steps

### Step 1

Created the investigation workspace.

**Evidence:**

- `C:\TimeStompLab`

---

### Step 2

Created sample files.

**Evidence:**

- Payroll.xlsx
- Employees.txt
- IncidentReport.docx

---

### Step 3

Recorded original timestamps.

**Observation:**

All files showed the current system date and time.

---

### Step 4

Modified timestamps for **IncidentReport.docx** using PowerShell.

**Observation:**

Creation, Last Write, and Last Access timestamps were changed to **01 January 2021**.

---

### Step 5

Verified timestamps using PowerShell.

**Observation:**

Only IncidentReport.docx displayed modified historical timestamps.

---

### Step 6

Verified timestamps through Windows File Properties.

**Observation:**

PowerShell output matched the timestamps displayed within File Properties.

---

### Step 7

Correlated forensic evidence.

| Evidence | Observation |
|-----------|-------------|
| Original timestamps | Current system date |
| Modified timestamps | Historical date |
| File Properties | Confirmed timestamp modification |
| PowerShell | Confirmed successful manipulation |

---

## Evidence Summary

Collected:

- Investigation folder
- Sample files
- Original timestamps
- Modified timestamps
- PowerShell outputs
- File Properties screenshots

---

## Analyst Observations

The investigation demonstrated that:

- Windows timestamps can be modified using native PowerShell.
- Time Stomping affects file metadata presented to investigators.
- Timestamp inconsistencies can indicate anti-forensics activity.
- Timestamp evidence should always be correlated with additional artifacts before reaching investigative conclusions.

---

## Conclusion

The investigation successfully demonstrated Windows Time Stomping by modifying file timestamps, validating the altered metadata through PowerShell and File Properties, and documenting how timestamp manipulation may be identified during a forensic investigation.
