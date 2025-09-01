## Experiment 1:  Evidence Acquisition Using AccessData FTK Imager

### Aim
The aim of this experiment is to demonstrate the process of **evidence acquisition** from a digital storage device using **AccessData FTK Imager**. The goal is to create a forensically sound image of the target media, preserving the original data's integrity and ensuring it can be used in a legal context. This involves generating a bit-for-bit copy of the data, including hidden, deleted, and unallocated space, and creating a **hash value** to verify the image's authenticity.

---

### Description
**FTK Imager** is a free, stand-alone tool used for data previewing and disk imaging. It's a critical tool in **digital forensics** because it allows an investigator to acquire a complete, forensically sound image of a hard drive or other storage media. This process is non-intrusive and ensures that no changes are made to the original evidence. The resulting image file can be in various formats, such as `.e01` (EnCase format) or `.dd` (raw format). The integrity of the acquired data is paramount. The tool calculates a **cryptographic hash** (like MD5 or SHA1) of the source drive before and after the imaging process. This hash acts as a **digital fingerprint**, ensuring that the data in the acquired image is an exact match to the original source. Any discrepancy in the hash value indicates that the data was altered, rendering the evidence inadmissible in court. 

---

### Procedure

1.  **Launching FTK Imager:**
    * Open **FTK Imager** on the forensic workstation.
![alt text](<screenshot/Screenshot 2025-08-31 191052.png>)
    * From the "File" menu, select **"Create Disk Image."**
![alt text](<screenshot/Screenshot 2025-08-31 191125.png>)

2.  **Selecting the Source:**
    * A dialog box will appear asking for the source of the image.
    * Select **"Physical Drive"** and click "Next."
![alt text](<screenshot/Screenshot 2025-08-31 191145.png>)    
    * Choose the connected source drive (the evidence) from the list. It will typically be identified by its make, model, or serial number.
![alt text](<screenshot/Screenshot 2025-08-31 191213.png>)    

3.  **Configuring the Image:**
    * Click "Add" to specify the destination for the image file.
![alt text](<screenshot/Screenshot 2025-08-31 191251.png>)    
    * Select the **"Image Type"** you want to create (e.g., `E01`, `DD`). `E01` is often preferred due to its ability to include case information and segment large images.
![alt text](<screenshot/Screenshot 2025-08-31 191303.png>)    
    * Provide **case information** such as the Case Number, Evidence Item Number, and Investigator Name. This metadata is crucial for maintaining the chain of custody.
![alt text](<screenshot/Screenshot 2025-08-31 191322.png>)    
    * Choose a destination path on the designated storage drive.
![alt text](<screenshot/Screenshot 2025-08-31 191440.png>)    
    * Provide a filename for the image and set a **fragment size** if desired (useful for segmenting large images for easier storage and transfer).


4.  **Acquisition:**
    * Initiate the imaging process by clicking "Start." FTK Imager will begin to create the bit-for-bit copy.
![alt text](<screenshot/Screenshot 2025-08-31 191648.png>)    
    * As the imaging progresses, FTK Imager will calculate a **hash value** (MD5 and/or SHA1) of the source data.