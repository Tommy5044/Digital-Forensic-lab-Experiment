## Experiment 3: Network Traffic Capture and Analysis using Wireshark

### Aim
The goal of this experiment is to learn how to **capture and analyze network traffic** passing through an interface using the open-source tool **Wireshark**. This process is fundamental to understanding network communication, identifying protocol behavior, and troubleshooting connectivity issues.

***

### Description
**Wireshark** is a widely-used and powerful network protocol analyzer. It allows users to see what's happening on their network at a microscopic level by capturing packets in real-time. Think of it as a digital magnifying glass for your network. When Wireshark is running, it listens to a network interface and copies every packet that passes through it, displaying the packet data in a human-readable format. This capability is invaluable for cybersecurity professionals, network administrators, and developers. It can be used to monitor network security, debug protocol implementations, and learn how various applications communicate. Wireshark can filter packets based on specific criteria, allowing an investigator to focus on relevant data and ignore extraneous traffic. 

***

### Procedure
1.  **Preparation:**
    * Download and install **Wireshark** on your computer.
    * Ensure you have the necessary administrative privileges to capture packets on your network interface.

2.  **Launching Wireshark and Selecting an Interface:**
    * Open Wireshark. The main screen will display a list of all available network interfaces (e.g., Wi-Fi, Ethernet).
    * Choose the interface you want to monitor. For most users, this will be the active Wi-Fi or Ethernet connection. The graph next to each interface shows the level of network activity.
![alt text](<screenshot 3/Screenshot 2025-09-01 152126.png>)    
    * Click on the selected interface to start the packet capture.

3.  **Capturing Network Traffic:**
    * Wireshark will immediately begin capturing packets. The middle pane will show a live stream of incoming and outgoing packets.
![alt text](<screenshot 3/Screenshot 2025-09-01 152211.png>)    
    * At this point, perform a task that generates network traffic, such as opening a website, using a chat application, or pinging a server.
    * Once you have captured enough data, click the **"Stop"** button (red square icon) to end the capture.

4.  **Analyzing the Captured Packets:**
    * The top pane lists the captured packets. The middle pane shows the details of a selected packet in various protocol layers (e.g., Ethernet, IP, TCP/UDP). The bottom pane displays the raw data of the packet in hexadecimal and ASCII.
![alt text](<screenshot 3/Screenshot 2025-09-01 152236.png>)    
    * Use the **"Filter"** bar at the top to narrow down your search. For example, type **"http"** to see only HTTP traffic, or **"dns"** to view DNS queries.
![alt text](<screenshot 3/Screenshot 2025-09-01 152842.png>)    
    * Right-click on a packet to follow a specific conversation (**"Follow TCP Stream"** or **"Follow UDP Stream"**) to see all packets related to a single communication.
![alt text](<screenshot 3/Screenshot 2025-09-01 153048.png>)    

5.  **Saving the Capture:**
    * Save the captured data as a `.pcap` file for later analysis by going to **File -> Save As**.
![alt text](<screenshot 3/Screenshot 2025-09-01 153228.png>)    

***

### Result
The experiment successfully captured and displayed real-time network traffic on a specified interface. The captured data was filtered and analyzed, revealing the details of various network protocols in action.