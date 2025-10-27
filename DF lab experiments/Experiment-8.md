# Experiment-8: Use Steg-Expose to detect hidden data in images

## Aim
Use Steg-Expose to scan images for steganographic content and follow up with targeted extraction and verification steps.

## Description
This experiment demonstrates a streamlined workflow to detect possible steganography using Steg-Expose, then confirm and extract hidden data using complementary tools (exiftool, binwalk, steghide, hex analysis). The focus is on automated detection, triage of suspicious files, and preserving extracted artifacts.

## Tools Used
- Steg-Expose (StegExpose.jar)
- exiftool, file
- binwalk, strings, hexdump (or xxd)
- steghide (for format-specific extraction)
- StegSolve (for visual bitplane inspection)
- Hash utilities (md5sum, sha1sum)
- Java Runtime Environment, shell environment

## Procedure
1. Prepare environment:
   - Ensure Java and required utilities are installed and Steg-Expose (StegExpose.jar) is available in the working folder.
   - ![Environment Setup](Screenshot%208/Screenshot_2025-07-30_01_06_49.png)

2. Collect and catalog images:
   - Place candidate images in a working directory and compute hashes for each file.
   - ![Catalog Images](Screenshot%208/Screenshot_2025-10-27_14_25_04.png)

3. Run Steg-Expose scan:
   - Example: `java -jar StegExpose.jar -r ./images/ -o steg_report.csv` (scan a directory and produce a report).  
   - Or scan a single file: `java -jar StegExpose.jar image.png`
   - Review the report for files flagged as suspicious or with a high detection score.
   - ![Steg-Expose Scan](Screenshot%208/Screenshot_2025-10-27_14_25_07.png)

4. Quick metadata and header checks:
   - Run `exiftool image.png` and `file image.png` to check for anomalies and unexpected container types.
   - ![Metadata Check](Screenshot%208/Screenshot_2025-10-27_14_25_09.png)

5. Triage flagged images:
   - For each suspicious file, run binwalk (`binwalk -e file`) and strings/hex searches to look for embedded file signatures (PK, GIF89a, %PDF, etc.).
   - ![Binwalk Analysis](Screenshot%208/Screenshot_2025-10-27_14_25_20.png)

6. Visual and bit-plane inspection:
   - Open the image in StegSolve to inspect color planes and bitplanes for hidden content or overlays.
   - ![StegSolve Inspection](Screenshot%208/Screenshot_2025-10-27_14_25_22.png)

7. Attempt targeted extraction:
   - If a steganographic container is suspected, try steghide (`steghide extract -sf image.jpg -p <password>`) or other extraction tools based on the discovered signature.
   - Save any recovered payloads to an output folder and record the extraction method.
   - ![Steghide Extraction](Screenshot%208/Screenshot_2025-10-27_14_25_40.png)

8. Verify and document:
   - Hash original images and any extracted payloads (`md5sum` / `sha1sum`).
   - Record Steg-Expose scores, tool versions, commands used, timestamps, and any notable findings.
   - ![Hash Verification](Screenshot%208/Screenshot%202025-10-27%20235849.png)

9. Organize artifacts and report:
   - Store flagged images, extracted files, logs, and screenshots in the evidence directory.
   - Produce a short report summarizing files scanned, detections, extraction results, and recommended next steps.
   - ![Final Report](Screenshot%208/Screenshot_2025-10-27_14_25_59.png)

Notes:
- Steg-Expose indicates likelihood of hidden data; follow-up manual verification is required to avoid false positives.
- Maintain chain-of-custody and log all commands and timestamps during analysis.

## Result
- Images were scanned with Steg-Expose and suspicious files were identified.
- Follow-up inspection using exiftool, binwalk, StegSolve, and steghide produced either extracted payloads or ruled out hidden content.
- All findings, hashes, extraction artifacts, and commands were documented for reporting and further analysis.
