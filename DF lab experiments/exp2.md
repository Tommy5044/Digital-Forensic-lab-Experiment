## Experiment 2:  Recover deleted or damaged files from a storage device using Test Disk

### Aim
The purpose of this experiment is to demonstrate the process of **recovering deleted or damaged files** from a storage device using the open-source utility, **TestDisk**. The objective is to restore files that have been accidentally deleted or are inaccessible due to a corrupted file system, verifying the successful recovery by checking the restored data.

***

### Description
**TestDisk** is a powerful, free, and open-source command-line tool designed for data recovery. While it is primarily used for **recovering lost partitions** and making non-bootable disks bootable again, it also has a strong capability for recovering deleted files. It operates by analyzing the disk's structure, including the partition table and file system. Unlike a simple file undelete program, TestDisk can handle various scenarios, such as a corrupted boot sector or a damaged partition. It works on numerous file systems, including NTFS, FAT, and ext4. When a file is deleted, the operating system simply marks the space as available, but the data often remains until it is overwritten. TestDisk scans the disk for these fragments of data and can often rebuild the file, especially if the data was not fragmented.

***

### Procedure
1.  **Preparation:**
    * Download and run **TestDisk** from the official website. It is a portable application, so it doesn't require installation.
    * **Crucially, do not run TestDisk on the same drive you are trying to recover data from.** Use a separate bootable media or connect the target drive to another computer to avoid overwriting the very data you're trying to recover.
    * It is recommended to create a log file to record the actions and outcomes of the session.

2.  **Launching and Selecting the Disk:**
    * Open TestDisk with administrative privileges.
    * From the initial menu, select **"Create a new log file"** and press Enter.
![alt text](<screenshot 2/Screenshot 2025-09-01 142844.png>)    
    * The program will list all connected storage devices. Use the arrow keys to select the target device (e.g., the damaged or a USB drive) and press **"Proceed"**.
![alt text](<screenshot 2/Screenshot 2025-09-01 142909.png>)    

3.  **Analyzing the Partition:**
    * TestDisk will automatically detect the partition table type. Confirm the type, which is usually the highlighted default option.
![alt text](<screenshot 2/Screenshot 2025-09-01 142938.png>)    
    * Select the **"Advanced"** option from the main menu. This option allows for file recovery instead of partition repair.
![alt text](<screenshot 2/Screenshot 2025-09-01 144016.png>)    
    * Highlight the specific partition where the files were deleted and select **"Undelete"**.
![alt text](<screenshot 2/Screenshot 2025-09-01 144111.png>)    

4.  **Recovering the Files:**
    * The program will scan for deleted files. Files that are potentially recoverable will be listed, often in red.
    * Navigate to the directory where the deleted files were located.
![alt text](<screenshot 2/Screenshot 2025-09-01 143007.png>)    
    * Use the arrow keys to highlight the files you wish to recover. Press the **"C"** key to copy the selected file.
![alt text](<screenshot 2/Screenshot 2025-09-01 143030.png>)    
    * You will be prompted to choose a destination to save the recovered files. Select a location on a **different drive** to prevent further data corruption.
![alt text](<screenshot 2/Screenshot 2025-09-01 143156.png>)    
    * Press **"C"** again to confirm and start the recovery process.
![alt text](<screenshot 2/Screenshot 2025-09-01 143214.png>)    

5.  **Completion:**
    * Once the recovery is complete, a confirmation message will appear.
![alt text](<screenshot 2/Screenshot 2025-09-01 143939.png>)    
    * Exit TestDisk and navigate to the destination folder to verify the recovered files.
![alt text](<screenshot 2/Screenshot 2025-09-01 143956.png>)    

***

### Result
The experiment successfully recovered deleted files from the target device, restoring them to a separate storage location. The recovered files were verified as intact and accessible, demonstrating the effectiveness of TestDisk for data recovery.