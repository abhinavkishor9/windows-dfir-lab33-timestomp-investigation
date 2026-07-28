# Troubleshooting Notes

## Issue 1

Investigation folder not found.

### Cause

Folder was not created before creating sample files.

### Resolution

Create the folder first:

```powershell
mkdir C:\TimeStompLab
```

---

## Issue 2

Unable to locate sample files.

### Cause

Incorrect filename or missing file.

### Resolution

Verify contents:

```powershell
Get-ChildItem C:\TimeStompLab
```

---

## Issue 3

PowerShell returned "Cannot find path".

### Cause

Incorrect file path supplied to `Get-Item`.

### Resolution

Verify the exact filename before modifying timestamps.

---

## Issue 4

Timestamp values did not change.

### Cause

Incorrect PowerShell syntax or file object not loaded.

### Resolution

Retrieve the file object first:

```powershell
$file = Get-Item "C:\TimeStompLab\IncidentReport.docx"
```

Then modify the timestamps.

---

## Issue 5

File Properties showed unexpected timestamps.

### Cause

File Explorer had not refreshed.

### Resolution

Close and reopen the Properties window or refresh File Explorer.

---

## Issue 6

Cleanup failed.

### Cause

A file remained open during deletion.

### Resolution

Close any open files and remove the investigation folder:

```powershell
Remove-Item C:\TimeStompLab -Recurse -Force
```
