# Ex. No. 9 — Use Process Explorer to Identify Suspicious Processes

## Digital Forensics Lab

### Aim / Description

**Process Explorer** is a Windows system-monitoring tool from Microsoft Sysinternals that provides detailed information about running processes.

It can be used to monitor processes, troubleshoot applications, and investigate potentially suspicious activities by examining process details such as:

* Process hierarchy
* Process ID (PID)
* CPU usage
* Memory usage
* Digital signatures
* File paths
* Company information
* Network activity

This experiment demonstrates how to use Process Explorer to identify and investigate potentially suspicious processes on a Windows system.

---

# Prerequisites

The following are required:

* Windows operating system
* Process Explorer
* Administrator privileges
* Internet connection for online process verification
* Trusted antivirus software

---

# 1. Download and Set Up Process Explorer

## 1.1 Download Process Explorer

Download **Process Explorer** from the official Microsoft Sysinternals website.

The downloaded package is provided as a ZIP file.

---

## 1.2 Extract the Program

Extract the downloaded ZIP file to a suitable folder.

Example:

```text id="m1xj3r"
ProcessExplorer/
├── procexp.exe
├── procexp64.exe
└── ...
```

---

## 1.3 Run Process Explorer

Open the extracted folder.

For a 64-bit Windows system:

```text id="8q7v5k"
procexp64.exe
```

For a 32-bit Windows system:

```text id="m7v9d3"
procexp.exe
```

Right-click the appropriate executable and select:

```text
Run as Administrator
```

The experiment specifies running `procexp64.exe` or `procexp.exe` as Administrator depending on the system architecture.

---

# 2. Understand the Process Explorer Interface

When Process Explorer starts, it displays currently running processes.

The interface provides information about:

* Process hierarchy
* CPU usage
* Memory usage
* Process ID
* Process status
* Process information

The main window displays processes in a tree structure, where child processes appear under their parent processes.

---

# 3. Understand Process Colors

Process Explorer uses colors to provide visual information about processes.

| Color      | Meaning                                             |
| ---------- | --------------------------------------------------- |
| Pink       | Suspended processes                                 |
| Light Blue | Processes running under the same user               |
| Dark Blue  | Services or processes running under system accounts |
| Green      | New processes                                       |
| Red        | Processes that have just exited                     |

The experiment notes that rapidly appearing and disappearing green processes may require investigation.

---

# 4. Examine Process Information

Process Explorer provides columns containing information such as:

```text
PID
CPU Usage
Memory Usage
Process Name
Description
Company Name
```

The Process ID (PID) can be used to uniquely identify a running process.

---

# 5. Identify Unfamiliar Processes

Scan the process list and look for processes that are not recognized.

Example:

```text
randomname123.exe
```

An unfamiliar process does not automatically mean that it is malicious. It should be investigated using additional evidence.

Look for:

* Unusual process names
* Unexpected parent-child relationships
* Unknown company names
* Unusual resource consumption
* Suspicious file locations
* Missing or invalid digital signatures

The lab document recommends examining unfamiliar process names because malware may use legitimate-looking or unusual names.

---

# 6. Verify Digital Signatures

Digital signatures can help determine whether an executable was signed by a software publisher.

To check a process:

1. Right-click the process.
2. Select **Properties**.
3. Open the **Image** tab.
4. Check the digital signature information.

A missing or invalid signature should be treated as a reason for further investigation rather than conclusive proof of malware.

The experiment specifically instructs checking the Image tab for a valid digital signature.

---

# 7. Check the Process File Path

Open the properties of the suspicious process and examine its file path.

Example of a normal Windows system location:

```text
C:\Windows\System32
```

A process running from an unusual location such as a temporary or random user directory may require additional investigation.

Example:

```text
C:\Users\User\AppData\Local\Temp\
```

The original experiment recommends checking whether the process is located in a legitimate directory.

---

# 8. Monitor CPU, Memory, and Disk Usage

Examine the resource usage columns in Process Explorer.

Look for processes with unusually high:

```text
CPU
Memory
Disk
```

For example:

```text
Process: suspicious.exe
CPU:     95%
Memory:  800 MB
```

High resource usage alone does not establish that a process is malicious. It should be considered together with other process characteristics.

The experiment identifies unexplained high CPU, memory, or disk usage as a reason for further investigation.

---

# 9. Check Description and Company Name

Examine the following information:

```text
Description
Company Name
```

Legitimate processes generally contain recognizable descriptions and publisher information.

Investigate processes that contain:

* Missing descriptions
* Unknown company names
* Suspicious publisher information

The lab document recommends examining these fields when investigating suspicious processes.

---

# 10. Check Network Activity

Some processes may communicate with external systems.

To examine network activity:

1. Right-click the process.
2. Select **Properties**.
3. Open the **TCP/IP** tab.
4. Review the available network connections.

Look for:

* Unexpected external connections
* Unknown remote addresses
* Unusual network activity

Unexpected connections may indicate that additional investigation is necessary.

---

# 11. Search for Information About a Suspicious Process

If a process appears suspicious:

1. Record the exact process name.
2. Search for the process name online.
3. Check trusted malware-analysis databases.
4. Compare the process information with known legitimate software.

Example:

```text
randomname123.exe
```

Possible resources include:

* VirusTotal
* ProcessLibrary
* Microsoft documentation
* Software vendor documentation

The original experiment recommends searching for unfamiliar processes and checking online malware databases such as VirusTotal or ProcessLibrary.

---

# 12. Handle a Suspicious Process

If investigation provides sufficient evidence that a process is malicious, Process Explorer provides options for managing the process.

## 12.1 Kill the Process

Right-click the process and select:

```text
Kill Process
```

This terminates the process.

---

## 12.2 Suspend the Process

If further investigation is required, the process can be suspended.

Right-click the process and select:

```text
Suspend
```

Suspending the process can prevent it from continuing to execute while the investigation is performed.

---

## 12.3 Examine the Source File

Use the file path shown in the process properties to locate the executable.

If the file has been confirmed as malware, follow the organization's malware-removal and evidence-preservation procedures before deleting it.

The original experiment describes killing, suspending, and removing a confirmed malicious executable, while also warning that some malware may prevent deletion.

---

# 13. Scan the System

After investigating suspicious processes, perform a full system scan using trusted security software.

Examples include:

```text
Windows Defender
Malwarebytes
```

Perform an in-depth scan of the system to identify additional threats.

The experiment recommends running a full antivirus scan and using malware-removal tools after terminating suspicious processes.

---

# 14. Example of Identifying a Suspicious Process

Consider a process named:

```text
randomname123.exe
```

During the investigation:

### Step 1 — Resource Usage

The process is observed using unusually high CPU resources.

```text
CPU Usage: High
```

### Step 2 — File Location

The process is found running from an unexpected folder rather than a normal system directory.

### Step 3 — Network Activity

The TCP/IP tab shows connections to unknown external IP addresses.

### Step 4 — Online Verification

A search of the process name indicates that it may be associated with malware.

### Step 5 — Response

After confirmation and appropriate evidence-preservation procedures, the suspicious process can be terminated and the associated file handled according to the investigation procedure.

This follows the example workflow described in the uploaded experiment.

---


# Result

Running processes were successfully monitored and analyzed using **Process Explorer**.

Process details including:

* Digital signatures
* File paths
* Resource usage
* Network activity

were examined to identify potentially suspicious processes.

---
## Screenshots :
<img width="1280" height="720" alt="WhatsApp Image 2026-09-22 at 1 16 01 AM" src="https://github.com/user-attachments/assets/ee63d71c-32d4-4039-afae-6be6b122c442" />
<img width="1280" height="720" alt="WhatsApp Image 2026-09-<img width="1280" height="720" alt="WhatsApp Image 2026-09-21 at 9 58 02 PM (2)" src="https://github.com/user-attachments/assets/db19ef09-2095-440e-83b9-3b3779fe0df4" />
<img width="1280" height="720" alt="WhatsApp Image 2026-09-21 at 9 58 02 PM (2)" src="https://github.com/user-attachments/assets/e7a4c96f-b752-4518-beaa-e922ed19c0aa" />
<img width="1280" height="720" alt="WhatsApp Image 2026-09-21 at 9 58 03 PM" src="https://github.com/user-attachments/assets/8e78dcf1-6662-4880-936b-406b551db109" />
<img width="1600" height="900" alt="WhatsApp Image 2026-09-21 at 9 57 54 PM (1)" src="https://github.com/user-attachments/assets/60f9e650-9441-4b04-9d3e-24926471a566" />
