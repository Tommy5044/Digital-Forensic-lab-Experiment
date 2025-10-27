# Experiment-9: Use Process Explorer to identify suspicious processes

## Aim
Use Process Explorer to inspect running processes, identify suspicious behavior (unexpected parent/child relationships, unsigned binaries, unusual handles or network activity), and document findings for further analysis.

## Description
This experiment demonstrates how to use Process Explorer (Sysinternals) to triage running processes on a Windows host. Steps include launching Process Explorer with administrative privileges, examining process properties, verifying signatures, checking network connections and loaded DLLs, comparing hashes with VirusTotal, and recording evidence with screenshots and hashes.

## Tools Used
- Process Explorer (Sysinternals)
- Process Monitor / Autoruns (optional for deeper triage)
- VirusTotal (web/API) or VTDesktop for hash checks
- sigcheck (Sysinternals) or sigverif for signature checks
- Hash utilities (certutil or PowerShell Get-FileHash)
- Screenshot tool and text editor for notes

## Procedure
1. Prepare environment:
   - Download Process Explorer and run as Administrator.
   -![alt text](<Screenshot 9/Screenshot 2025-10-28 000837.png>)

2. Capture baseline and context:
   - Note system time, user, and recent changes (software installs, alerts).
   - Optionally save a snapshot (File → Save) for offline review.
   -![alt text](<Screenshot 9/Screenshot 2025-10-28 000901.png>)

3. Identify suspicious processes visually:
   - Look for unknown process names, high CPU/IO, unusual parent processes (e.g., explorer.exe spawning cmd.exe hidden).
   - Expand process tree to view parent/child relationships.
   -![alt text](<Screenshot 9/Screenshot 2025-10-28 000919.png>)

4. Inspect properties of a suspect process:
   - Double-click process → check Image Path, Command Line, User, Company Name, and Description.
   - Check the PID, Start Time, CPU, and Threads.
   -![alt text](<Screenshot 9/Screenshot 2025-10-28 001049.png>)

5. Verify digital signature and file details:
   - In the process properties, open the "Image" tab and view the digital signature status.
   - Use sigcheck or Get-FileHash to compute a file hash: `Get-FileHash -Algorithm SHA256 "C:\path\to\binary.exe"`
   -![alt text](<Screenshot 9/Screenshot 2025-10-28 001133.png>)

6. Check loaded DLLs and handles:
   - Use the "DLLs" tab to inspect loaded libraries for suspicious or unsigned modules.
   - Use the "Handles" tab to view files, registry keys, or named pipes in use.
   -![alt text](<Screenshot 9/Screenshot 2025-10-28 001224.png>)

7. Review network activity:
   - Right-click → "Properties" → "TCP/IP" (or use Process Explorer's lower pane) to view open connections and ports.
   - Correlate with firewall logs or netstat output.
   -![alt text](<Screenshot 9/Screenshot 2025-10-28 001305.png>)

8. Cross-check with VirusTotal:
   - Submit the file hash or upload binary to VirusTotal; record detection ratio and AV names.
   - If using VirusTotal API or VTDesktop, document the result and timestamp.
   -![alt text](<Screenshot 9/Screenshot 2025-10-28 001404.png>)

9. Correlate with other tools:
   - Use Autoruns to check persistence entries or Process Monitor to capture file/registry activity if needed.
   - Save relevant logs and evidence.

10. Document and preserve:
   - Save Process Explorer snapshot or export process list.
   - Record file paths, hashes, parent process, timestamps, VirusTotal results, and screenshots.
   - Store artifacts in case folder and generate a short report.
   -![alt text](<Screenshot 9/Screenshot 2025-10-28 001432.png>)

Notes:
- Run as Administrator to view all process details.
- Avoid terminating processes without case authorization; document actions before remediation.
- Maintain chain-of-custody for any collected binaries.

## Result
- Suspicious processes were identified via anomalies in names, parentage, signatures, handles, DLLs, and network connections.
- Relevant binaries were hashed and checked against VirusTotal; findings were documented with screenshots and logs.
- Evidence (snapshots, hashes, VirusTotal reports) was saved for further forensic analysis or escalation.
