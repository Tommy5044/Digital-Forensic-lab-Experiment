# Experiment-6: Use Sleuth Kit to analyze digital evidence

## Aim
Use Sleuth Kit command-line utilities to examine a disk image, identify partitions and filesystems, list and recover files (including deleted items), produce a timeline, and record findings.

## Description
This experiment demonstrates basic Sleuth Kit (tsk) workflows for low-level forensic analysis: partition discovery, filesystem inspection, file listing (including deleted entries), file extraction, timeline creation, and hashing/verification. The steps are command-oriented so they can be reproduced in a lab environment.

## Tools
- Sleuth Kit (tsk tools such as mmls, fsstat, fls, icat, tsk_recover, blkcat, mactime)
- Unix-like shell (Linux/WSL/macOS) or equivalent Windows environment with Sleuth Kit
- Disk image file (E01/RAW/aff or similar)
- Hash utilities (md5sum, sha1sum) and a text editor for notes

## Procedure
1. Prepare environment:
   - Install or verify Sleuth Kit is available (e.g., tsk version).
   - ![alt text](<screenshot 6/Screenshot 2025-10-27 225847.png>)

2. Identify partition layout:
   - Use mmls to view partitions: `mmls image.dd`
   - Note partition offsets and sizes.
   - ![alt text](<screenshot 6/Screenshot 2025-10-27 230417.png>)

3. Inspect filesystem metadata:
   - Run fsstat on the partition offset: `fsstat -o <offset> image.dd`
   - Record filesystem type and important parameters.
   - ![alt text](<screenshot 6/Screenshot 2025-10-27 230521.png>)

4. List files (including deleted):
   - Use fls to enumerate files and deleted entries: `fls -o <offset> -r image.dd > file_list.txt`
   - Review the file list for items of interest.
   - ![alt text](<screenshot 6/Screenshot 2025-10-27 231247.png>)

5. Extract specific files:
   - Use icat to extract a file by inode: `icat -o <offset> image.dd <inode> > recovered_file`
   - Verify file type and integrity.
   - ![alt text](<screenshot 6/Screenshot 2025-10-27 231454.png>)

6. Recover bulk files:
   - Use tsk_recover to extract recoverable files to a directory: `tsk_recover -o <offset> image.dd output_dir/`
   - Inspect recovered contents for relevant artifacts.

7. Read raw blocks or carve data:
   - Use blkcat to read raw filesystem blocks if needed: `blkcat -o <offset> image.dd <block> > block.bin`

8. Create a timeline:
   - Generate body file entries: `fls -o <offset> -m / image.dd | awk '{print $0}' > bodyfile.txt`
   - Run mactime to build a timeline: `mactime -b bodyfile.txt > timeline.csv`

9. Hashing and verification:
   - Compute hashes for image or recovered files: `md5sum image.dd` / `sha1sum recovered_file`
   - Record hashes in case notes.

10. Document findings and export:
   - Summarize notable files, recovered deleted items, timeline highlights, and hashes.
   - Export logs and recovered files for reporting.


## Result
- Partition layout and filesystem metadata identified.
- File listings (including deleted entries) produced.
- Target files recovered and verified with hashes.
- A timeline of key filesystem events created.
- Findings documented and exported for further analysis or reporting.
