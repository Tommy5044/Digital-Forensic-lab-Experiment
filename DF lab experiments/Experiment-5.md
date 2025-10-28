# Experiment-5: Use Autopsy to create a case and import evidence

## Aim
Create and set up a new case in Autopsy, import a digital evidence source (disk image, logical files, or a device), run the initial ingest, and review the first analysis results.

## Description
This exercise takes you step-by-step through the common Autopsy workflow: starting the application, creating a case with basic metadata, adding a data source, choosing ingest modules, watching the ingest process, and looking at the initial artifacts and reports. It’s written to be practical and easy to follow — ideal for a hands-on lab session.

## Tools
- Autopsy (version used: e.g., 4.x)
- Evidence file(s) — disk image (E01/RAW), logical file set, or device
- Host OS (Windows/Linux) with Autopsy installed

## Procedure
1. Launch Autopsy.
   

2. Create a new case:
   - File → New Case.
   - Enter Case Name, Case Number (optional), Examiner, and Case Location.
   - Click "Create".
   !![alt text](<screenshot 5/Screenshot 2025-10-21 095716.png>)
   !![alt text](<screenshot 5/Screenshot 2025-10-21 095931.png>)

3. Create or open a case directory:
   - Confirm the default case folder or choose a custom location.
   ![alt text](<screenshot 5/Screenshot 2025-10-21 100458.png>)

4. Add a data source (import evidence):
   - Click "Add Data Source".
   - Select the appropriate data source type (Disk Image, Logical Files, Local Disk, etc.).
   - For disk images, choose the image file (E01/RAW/aff or similar).
   - Configure image options if required and proceed.
   ![alt text](<screenshot 5/Screenshot 2025-10-21 100737.png>)
  ![alt text](<screenshot 5/WhatsApp Image 2025-10-21 at 12.35.46_93afaa1e.jpg>)
5. Configure ingest modules:
   - Select modules to run (File Type Identification, Hash Lookup, EXIF, Keywords, Timeline, etc.).
   - Optionally use custom settings or default profile.
   - Start ingest.
   ![alt text](<screenshot 5/Screenshot 2025-10-21 122244.png>)
  ![alt text](<screenshot 5/Screenshot 2025-10-21 122904.png>)

6. Monitor ingest and initial results:
   - Observe progress bar and logs.
   - After completion, review Case Dashboard, Extracted Files, File Types, Recent Activity, and Artifacts.
   ![alt text](<screenshot 5/Screenshot 2025-10-21 123825.png>)
   ![alt text](<screenshot 5/Screenshot 2025-10-21 123926.png>)
7. Save or export findings:
   - Export reports or artifacts as needed (HTML, CSV, or other formats).
   ![alt text](<screenshot 5/Screenshot 2025-10-21 123913.png>)


## Result
- A new Autopsy case was created with the specified metadata.
- The selected evidence was successfully imported and ingested.
- Autopsy produced parsed artifacts (file listings, extracted metadata, timeline entries, keyword hits, and other findings) available in the Case Dashboard.
- Reports and extracted items can be exported for further analysis or presentation.

