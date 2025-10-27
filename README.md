# 🔍 Digital Forensic Lab Experiments

<div align="center">

![Digital Forensics](https://img.shields.io/badge/Digital-Forensics-blue?style=for-the-badge&logo=security&logoColor=white)
![Lab Manual](https://img.shields.io/badge/Lab-Manual-green?style=for-the-badge&logo=book&logoColor=white)
![Open Source](https://img.shields.io/badge/Open-Source-orange?style=for-the-badge&logo=github&logoColor=white)

*A comprehensive collection of hands-on digital forensics experiments for cybersecurity education*

</div>

---

## 📋 Table of Contents

- [🎯 Overview](#-overview)
- [🧪 Experiments](#-experiments)
- [🛠️ Tools Used](#️-tools-used)
- [📚 Learning Objectives](#-learning-objectives)
- [🚀 Getting Started](#-getting-started)
- [📖 How to Use](#-how-to-use)
- [🔧 Prerequisites](#-prerequisites)
- [🤝 Contributing](#-contributing)
- [📄 License](#-license)

---

## 🎯 Overview

This repository contains a comprehensive collection of **10 hands-on digital forensics experiments** designed for cybersecurity students, professionals, and researchers. Each experiment provides step-by-step procedures, tool configurations, and real-world scenarios to build practical skills in digital evidence acquisition, analysis, and reporting.

## 🧪 Experiments

### 🔹 **Experiment 1: Evidence Acquisition Using AccessData FTK Imager**
**🎯 Objective:** Create forensically sound disk images for legal evidence preservation
- **Tools:** AccessData FTK Imager
- **Skills:** Disk imaging, hash verification, chain of custody
- **Output:** Forensic disk images (.E01/.DD format)

### 🔹 **Experiment 2: File Recovery Using TestDisk**
**🎯 Objective:** Recover deleted or damaged files from storage devices
- **Tools:** TestDisk
- **Skills:** Data recovery, partition analysis, file system repair
- **Output:** Recovered files and partition tables

### 🔹 **Experiment 3: Network Traffic Analysis Using Wireshark**
**🎯 Objective:** Capture and analyze network communications for security investigation
- **Tools:** Wireshark
- **Skills:** Packet capture, protocol analysis, traffic filtering
- **Output:** Network traffic analysis reports (.pcap files)

### 🔹 **Experiment 4: Email Header Analysis and Spoofing Detection**
**🎯 Objective:** Analyze email headers to detect spoofing and trace email origins
- **Tools:** Microsoft Message Header Analyzer (MHA)
- **Skills:** Email forensics, header parsing, authentication verification
- **Output:** Email authenticity reports and spoofing detection

### 🔹 **Experiment 5: Digital Evidence Management Using Autopsy**
**🎯 Objective:** Create forensic cases and perform comprehensive evidence analysis
- **Tools:** Autopsy Digital Forensics Platform
- **Skills:** Case management, evidence ingestion, artifact analysis
- **Output:** Forensic case reports and extracted artifacts

### 🔹 **Experiment 6: File System Analysis Using Sleuth Kit**
**🎯 Objective:** Perform low-level file system analysis and timeline creation
- **Tools:** Sleuth Kit (TSK) command-line tools
- **Skills:** File system forensics, deleted file recovery, timeline analysis
- **Output:** File listings, recovered data, forensic timelines

### 🔹 **Experiment 7: Mobile Device Forensics Using AFLogical OSE**
**🎯 Objective:** Extract logical data from Android devices for forensic analysis
- **Tools:** AFLogical OSE, ADB (Android Debug Bridge)
- **Skills:** Mobile forensics, logical extraction, artifact verification
- **Output:** Extracted mobile data (contacts, SMS, call logs, app data)

### 🔹 **Experiment 8: Steganography Detection Using Steg-Expose**
**🎯 Objective:** Detect and extract hidden data from digital images
- **Tools:** Steg-Expose, StegSolve, steghide, exiftool, binwalk
- **Skills:** Steganography analysis, hidden data extraction, image forensics
- **Output:** Detected steganographic content and extracted payloads

### 🔹 **Experiment 9: Process Analysis Using Process Explorer**
**🎯 Objective:** Identify suspicious processes and malware behavior on Windows systems
- **Tools:** Process Explorer (Sysinternals), VirusTotal
- **Skills:** Process forensics, malware detection, system analysis
- **Output:** Process analysis reports and IOC identification

### 🔹 **Experiment 10: Malware Analysis Using Ghidra**
**🎯 Objective:** Reverse engineer and analyze malware using static analysis techniques
- **Tools:** Ghidra, Java Runtime Environment
- **Skills:** Reverse engineering, static malware analysis, code decompilation
- **Output:** Disassembled code, IOCs, malware behavior reports

---

## 🛠️ Tools Used

<div align="center">

| Category | Tools |
|----------|-------|
| **Disk Imaging** | FTK Imager, TestDisk |
| **Network Analysis** | Wireshark |
| **Email Forensics** | Microsoft Message Header Analyzer |
| **Digital Forensics Platforms** | Autopsy, Sleuth Kit |
| **Mobile Forensics** | AFLogical OSE, ADB |
| **Steganography** | Steg-Expose, StegSolve, steghide |
| **Process Analysis** | Process Explorer, VirusTotal |
| **Malware Analysis** | Ghidra, binwalk, strings |

</div>

---

## 📚 Learning Objectives

Upon completion of these experiments, students will be able to:

- ✅ **Acquire digital evidence** using industry-standard forensic imaging tools
- ✅ **Recover deleted data** from various storage media and file systems
- ✅ **Analyze network traffic** to identify security incidents and suspicious activity
- ✅ **Investigate email communications** and detect spoofing attempts
- ✅ **Manage digital forensic cases** using comprehensive analysis platforms
- ✅ **Perform file system analysis** and create forensic timelines
- ✅ **Extract mobile device data** for investigative purposes
- ✅ **Detect steganographic content** in digital media files
- ✅ **Identify malicious processes** and analyze system behavior
- ✅ **Reverse engineer malware** using static analysis techniques

---

## 🚀 Getting Started

### 1. **Clone the Repository**
```bash
git clone https://github.com/your-username/Digital-Forensic-lab-Experiment.git
cd Digital-Forensic-lab-Experiment
```

### 2. **Set Up Lab Environment**
- Set up isolated virtual machines for forensic analysis
- Install required tools (see individual experiment requirements)
- Prepare test data and sample files

### 3. **Choose Your Experiment**
Navigate to the `DF lab experiments` folder and select an experiment to begin.

---

## 📖 How to Use

Each experiment folder contains:

- 📄 **Detailed procedure** with step-by-step instructions
- 🖼️ **Screenshots** showing expected outputs and tool interfaces
- 📊 **Sample data** and test files (where applicable)
- 📋 **Results documentation** templates
- 🔍 **Analysis guidelines** and best practices

### Recommended Learning Path:
1. Start with **Experiment 1** (Evidence Acquisition) to understand forensic fundamentals
2. Progress through **Experiments 2-6** for core digital forensics skills
3. Advance to **Experiments 7-10** for specialized analysis techniques

---

## 🔧 Prerequisites

### **Hardware Requirements:**
- 8GB+ RAM recommended
- 100GB+ free disk space
- USB ports for external device testing
- Network interface for traffic analysis

### **Software Requirements:**
- Virtual machine software (VMware/VirtualBox)
- Windows and Linux operating systems
- Java Runtime Environment
- Administrative privileges for tool installation

### **Knowledge Prerequisites:**
- Basic understanding of computer systems
- Familiarity with command-line interfaces
- Knowledge of networking concepts
- Understanding of file systems

---

## 🤝 Contributing

We welcome contributions to improve and expand this digital forensics lab manual!

### Ways to contribute:
- 🐛 Report bugs or issues
- 💡 Suggest new experiments
- 📝 Improve documentation
- 🔧 Add new tools or techniques
- 📸 Contribute better screenshots

### Contribution Guidelines:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

<div align="center">

### 🎓 **Educational Purpose**
*This repository is intended for educational and research purposes only. Always ensure compliance with applicable laws and obtain proper authorization before conducting any forensic analysis.*

---

**📧 Contact:** [Your Email] | **🌐 Website:** [Your Website] | **🐛 Issues:** [GitHub Issues]

</div>

---

<div align="center">

**⭐ If you find this repository helpful, please consider giving it a star! ⭐**

</div>
