## Experiment 4: Email Header Analysis and Spoofing Detection using MHA

### Aim
The aim of this experiment is to demonstrate how to **analyze email headers** to trace an email's path and to **detect email spoofing** using a tool like the **Microsoft Message Header Analyzer (MHA)**. The objective is to verify an email's authenticity by examining its routing details. 🕵️‍♀️

***

### Description
An email header is a block of text at the top of an email that contains a log of its journey from sender to recipient. It's like a digital postmark on an envelope, providing a detailed record of every server the email passed through. This information includes the sender's details, the date and time, and a crucial list of "Received" headers, which show the path and timing of the email's delivery. **Email spoofing** is a technique where an attacker forges the sender's address to make the email appear to be from someone else, often for malicious purposes like phishing. By analyzing the raw email headers, one can uncover the true origin of the message and identify inconsistencies that point to spoofing. The **Microsoft Message Header Analyzer (MHA)** is a free, web-based tool that simplifies this process by parsing the complex header data and presenting it in a clear, readable format. It highlights key information, making it easier for a user to trace the email's route and spot potential fraud. 

***

### Procedure
1.  **Preparation:**
    * Access the email you want to analyze. This can be in any email client (Outlook, Gmail, etc.).
![alt text](<screenshot 4/Screenshot 2025-09-01 204639.png>)    
    * Locate the option to view the **raw email headers**. This is often found under "Show original," "View message source," or "View details."
    * **Copy the entire block of raw email header text** to your clipboard.
![alt text](<screenshot 4/Screenshot 2025-09-01 204653.png>) 
![alt text](<screenshot 4/Screenshot 2025-09-01 204708.png>)
![alt text](<screenshot 4/Screenshot 2025-09-01 204720.png>)

2.  **Launching MHA:**
    * Navigate to the **Microsoft Message Header Analyzer** website.
![alt text](<screenshot 4/Screenshot 2025-09-01 204743.png>)    
    * You will see a text box on the page.

3.  **Analyzing the Header:**
    * **Paste the copied email header text** into the text box.
![alt text](<screenshot 4/Screenshot 2025-09-01 204805.png>)    
    * Click the **"Analyze headers"** button.
    * The tool will parse the data and display a summary in a structured format below.

4.  **Interpreting the Results:**
    * **Review the "Received" headers.** These headers are added by each server the email passes through. Reading them from bottom to top shows the email's path from the original sender to the recipient.
![alt text](<screenshot 4/Screenshot 2025-09-01 204822.png>)   
![alt text](<screenshot 4/Screenshot 2025-09-01 204840.png>)
![alt text](<screenshot 4/Screenshot 2025-09-01 204906.png>)
![alt text](<screenshot 4/Screenshot 2025-09-01 204920.png>)

    * **Examine the "Received-SPF," "DKIM," and "DMARC" headers.** These are authentication standards used to prevent spoofing. A result of "Pass" or "None" is normal, but a "Fail" can be a strong indicator of spoofing.

    * **Compare the "From" field with the "Return-Path" or "Sender" fields.** In a spoofed email, the visible "From" address may not match the actual sending address or domain, which is a key sign of a forged email.
    * Look for **inconsistencies** such as unusual IP addresses, a discrepancy between the sending domain and the originating server's IP address, or strange routing paths.
![alt text](<screenshot 4/Screenshot 2025-09-01 204932.png>)    
![alt text](<screenshot 4/Screenshot 2025-09-01 204943.png>)
![alt text](<screenshot 4/Screenshot 2025-09-01 205000.png>)
![alt text](<screenshot 4/Screenshot 2025-09-01 205011.png>)

***

### Result
The experiment successfully analyzed the email headers using MHA, providing a clear path of the email's journey. Analysis of the parsed data correctly identified the email as either authentic or spoofed based on inconsistencies in the sender's information and authentication headers.