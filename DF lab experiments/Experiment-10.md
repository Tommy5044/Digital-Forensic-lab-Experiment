# Experiment-10: Use Ghidra to disassemble and analyze the malware code

## Aim
Use Ghidra to import, disassemble, decompile, and analyze a malware binary to identify behavior, control flow, indicators of compromise, and extract actionable artifacts.

## Description
This experiment describes a practical Ghidra workflow for static malware analysis: creating a project, importing the sample, configuring analysis options, using the disassembler and decompiler, inspecting strings/xrefs, renaming functions/variables, annotating code, scripting repetitive tasks, and exporting findings. Emphasis is on reproducible steps and evidence capture.

## Tools Used
- Ghidra (latest stable)
- Java Runtime Environment (required by Ghidra)
- Sample malware binary (isolated lab environment)
- Auxiliary tools: strings, binwalk, objdump, VirusTotal (for hashes), debugger (GDB/x64dbg) — optional
- Text editor for notes / report

## Procedure
1. Prepare analysis environment:
   - Ensure Ghidra and Java are installed in an isolated VM or analysis machine.
   - Compute and record sample hashes: `md5sum sample.bin` / `sha256sum sample.bin`
   -![alt text](<Screenshot 10/Screenshot From 2025-10-26 01-09-37.png>)

2. Create a Ghidra project:
   - Open Ghidra → File → New Project → Non-Shared Project → choose project folder.
   -![alt text](<Screenshot 10/Screenshot From 2025-10-26 01-17-47.png>)

3. Import the binary:
   - File → Import File → select sample binary.
   - Confirm detected file format and processor; override if necessary.
   -![alt text](<Screenshot 10/Screenshot From 2025-10-26 01-23-41.png>)

4. Configure auto-analysis:
   - On import, enable auto-analysis and choose relevant options (function ID, string analysis, data xrefs, decompiler).
   - Start analysis and monitor progress.
   -![alt text](<Screenshot 10/Screenshot From 2025-10-26 01-24-19.png>)
   -![alt text](<Screenshot 10/Screenshot From 2025-10-26 01-26-32.png>)

5. Explore CodeBrowser:
   - Use Symbol Tree to view functions, labels, and data.
   - Open decompiler window for high-level pseudocode of functions of interest.
   - Inspect disassembly, operands, and cross-references (Xrefs).
   -![alt text](<Screenshot 10/Screenshot From 2025-10-26 01-26-44.png>)
   ![alt text](<Screenshot 10/Screenshot From 2025-10-26 01-27-20.png>)

6. Identify entry points and suspicious functions:
   - Check main/startup routines, network-related functions, dynamic API resolves, suspicious string references (URLs, IPs, commands).
   - Use "References" and "Callers" to trace execution flow.
   -![alt text](<Screenshot 10/Screenshot From 2025-10-26 01-28-20.png>)

7. Rename and annotate:
   - Rename functions, define data types, add comments and bookmarks to document findings.
   - Create meaningful variable and function names based on observed behavior.
   -![alt text](<Screenshot 10/Screenshot From 2025-10-26 01-29-46.png>)
   ![alt text](<Screenshot 10/Screenshot From 2025-10-26 01-30-50.png>)

8. Use scripting and function signatures:
   - Run built-in Function ID or apply community signatures to identify known libraries.
   - Write or run Ghidra scripts (Python/Jython) for repetitive tasks (e.g., extract strings, export functions).
   -![alt text](<Screenshot 10/Screenshot From 2025-10-26 01-33-37.png>)
   ![alt text](<Screenshot 10/Screenshot From 2025-10-26 01-40-45.png>)

9. Cross-check and extract artifacts:
   - Extract embedded strings, configuration data, domains/IPs, and potential dropped filenames.
   - Cross-check hashes/domains with external services (VirusTotal, passive DNS).
   -![alt text](<Screenshot 10/Screenshot From 2025-10-26 01-41-16.png>)

10. Export and document findings:
   - Export disassembly snippets, decompiler output, annotated function list, and screenshots.
   - Record tool versions, commands, sample hashes, timestamps, and a short behavioral summary.
   -![alt text](<Screenshot 10/Screenshot From 2025-10-26 01-43-13.png>)
   ![alt text](<Screenshot 10/Screenshot From 2025-10-26 01-44-00.png>)

Notes:
- Perform analysis in an isolated environment; do not run malware on host.
- Preserve original sample and computed hashes for chain-of-custody.
- Use dynamic analysis (sandbox or debugger) only when safe and authorized.

## Result
- Malware binary imported and analyzed in Ghidra with key functions identified and annotated.
- Extracted artifacts (strings, IOCs, function summaries) documented and hashed.
- Report produced containing behavior summary, indicators of compromise, and recommended next steps for detection or remediation.
