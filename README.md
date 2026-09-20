# Diving-in-Process-explorer-
Practical endpoint analysis and threat triage using Sysinternals Process Explorer, featuring live VirusTotal integration, kernel process inspection, and digital signature verification.
# Windows Endpoint Triage: Process Explorer & VirusTotal Integration

## 1. Project Overview
A brief 2–3 sentence summary explaining what the project is: a hands-on investigation using Sysinternals Process Explorer to baseline running processes, triage binaries against VirusTotal, and analyze Windows security boundaries.

---

## 2. Objectives & Skills Demonstrated
Bullet points highlighting practical IT and security competencies:
* Live process monitoring and parent-child hierarchy mapping
* Direct API hash reputation queries via VirusTotal integration
* Distinguishing kernel protections (PPL) from permission errors
* Verifying Microsoft digital certificates to dismiss false positives

---

## 3. Environment & Tools
* **OS:** Windows 10 / 11
* **Tools Used:** 
  * Sysinternals Process Explorer (`procexp.exe`)
  * Sysinternals Process Monitor (`procmon.exe`)
  * VirusTotal API

---

## 4. Step-by-Step Walkthrough

### Step 1: Configuring Process Explorer
* Launching `procexp.exe` with administrative privileges.
* Adding key diagnostic columns: `Image Path`, `Company Name`, and `Working Set`.
* * <img width="4284" height="5712" alt="unnamed" src="https://github.com/user-attachments/assets/e6357df3-0ba8-4a5d-91ab-d246a6c38d05" />
  *

### Step 2: Enabling VirusTotal Integration
* Enabling hash checks via `Options` > `VirusTotal.com` > `Check VirusTotal.com`.
* Explaining how the tool queries hashes against multi-engine databases on the fly without uploading files.
* **

### Step 3: Analyzing Protected Kernel Processes
* Observing `[Access is denied]` on critical items (`smss.exe`, `csrss.exe`).
* Explanation: Protected Process Light (PPL) and kernel memory structures (`Registry`, `Memory Compression`) intentionally blocking user-mode inspection.

### Step 4: Investigating Potential Anomalies (False Positive Analysis)
* Case Study: Handling a `1/75` detection on `ssh-agent.exe`.
* Verification Process:
  1. Validated directory path (`C:\Windows\System32\OpenSSH\ssh-agent.exe`).
  2. Inspected properties and verified the authentic `Microsoft Windows` digital signature.
  3. Outcome: Identified heuristic false positive with no compromise.

---

## 5. Key Takeaways
A short 3–4 bullet recap of core lessons learned regarding endpoint hygiene, signature verification, and process isolation.
