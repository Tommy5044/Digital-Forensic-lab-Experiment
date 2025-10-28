# Experiment-7: Use AFLogical OSE to extract data from an Android device

## Aim
Perform a logical extraction from an Android device using AFLogical OSE and produce verified artifact exports for analysis.

## Description
This experiment documents the steps to use AFLogical OSE to collect logical artifacts (SMS, contacts, call logs, app data, media, etc.) from an Android device. It covers device preparation, running AFLogical OSE, transferring and verifying extracted data, and performing basic inspection of the outputs.

## Tools
- AFLogical OSE (script/jar as provided)
- adb (Android Debug Bridge)
- Host machine (Windows/Linux) with Java/Python if required by AFLogical OSE
- Hash utilities (md5sum, sha1sum) and a text editor
- Optional: SQLite viewer, forensic viewers for exported formats

## Procedure
1. Prepare device and host:
   - Enable Developer Options → USB Debugging on the Android device.
   - Ensure device is unlocked and accessible; note device model and Android version.
   - Verify adb connection: `adb devices`
   ![alt text](<screenshot%207/Screenshot%202025-10-27%20232429.png>)

2. Obtain AFLogical OSE:
   - Place AFLogical OSE files (script/jar) onto the host working directory.
   - Confirm required runtime (Java/Python) is available.
   - ![alt text](<screenshot%207/Screenshot%202025-10-27%20232603.png>)

3. Configure extraction parameters:
   - Review AFLogical OSE options (artifact categories, output folder).
   - Choose extraction scope (contacts, SMS, call logs, app data, media, system settings).
   - ![alt text](<screenshot%207/Screenshot%202025-10-27%20233156.png>)

4. Run AFLogical OSE:
   - Connect device via USB and accept any prompts on-device.
   - Execute extraction command, for example:
     - `adb shell` then run AFLogical OSE via available method, or
     - `java -jar AFLogicalOSE.jar -o output_dir` (adjust to your AFLogical OSE variant)
   - Monitor output for success messages and any errors.
   - ![alt text](<screenshot%207/Screenshot%202025-10-27%20233156.png>)

5. Retrieve and organize extracted data:
   - If extraction wrote to device storage, pull to host: `adb pull /sdcard/AFLogical_output ./evidence/`
   - Ensure the output directory contains expected folders/files (contacts.vcf, sms.xml, calllog.db, app folders).
   - ![alt text](<screenshot%207/Screenshot%202025-10-27%20233749.png>)

6. Verify integrity and document:
   - Compute hashes for the extraction archive/files: `md5sum` / `sha1sum`.
   - Record device details, AFLogical OSE version, command used, timestamps, and hash values.

7. Preliminary analysis:
   - Inspect common artifacts: open contacts.vcf, view sms.xml, examine calllog.db with SQLite tools.
   - Export or convert artifacts to analysis-friendly formats as needed.
   - Note any suspicious entries or items of investigative interest.

8. Preserve and report:
   - Store original extraction files, logs, and hashes in the case repository.
   - Produce a short report listing extracted artifact types, notable findings, and verification hashes.

Notes:
- Follow legal and organizational authorization before any acquisition.
- AFLogical OSE performs a logical extraction; it does not capture volatile memory or deleted data.
- If the device prompts for confirmation, record screenshots and user interactions.

## Result
- A logical extraction from the Android device was completed using AFLogical OSE.
- Extracted artifacts (contacts, SMS, call logs, app data, media) were collected, hashed, and documented.
- Initial inspection identified and exported relevant artifacts for further forensic analysis.
