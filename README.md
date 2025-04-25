<p align="center">
<img img width="260" alt="image" src="https://tse1.mm.bing.net/th/id/OIG3.ZsRTSLeL1.qmcEDs1Tb.?pid=ImgGn" alt="Enterprise Computer Imaging"/>
</p>

<h1><b>Enterprise Computer Imaging - PXE & USB Deployment</b></h1>

<h2>Overview</h2>

This repository provides a detailed guide on imaging computers using **PXE servers** and **USB drives**. It covers **enterprise provisioning techniques**, **network-based mass imaging**, and **manual deployment workflows**. Optional sections explore **DHCP configurations**, **PowerShell scripting**, and **Active Directory (AD) integration** for IT professionals.

For **related cloud-based imaging methods via Azure**, visit my repository:  
[Azure Computing and Networking](https://github.com/victoriadeery/azure-computing-and-networking)

---

<h2>Environments, Technologies, and Features Used</h2>

- **PXE Server** – Network-based mass imaging for enterprise IT setups  
- **USB Bootable Media** – Manual deployment for specialized images or backup scenarios  
- **Windows Deployment Services (WDS) (Optional)** – Streamlined imaging automation  
- **DHCP & TFTP Servers** – PXE setup requirements for network provisioning  
- **PowerShell Scripting (Optional)** – Automation for configuration tasks  
- **Active Directory (AD) Integration (Optional)** – Enterprise provisioning  

---

<h2>Operating Systems Used</h2>

- **Windows 10/11 (64-bit)**  
- **Windows Server (for PXE Boot Configuration - Optional)**  

---

<h2>List of Prerequisites</h2>

- **Network-connected PXE Server or Bootable USB Drive**  
- **Windows ISO file** from [Microsoft](https://www.microsoft.com/en-us/software-download/windows10)  
- **Imaging tools** (Macrium Reflect, Clonezilla, or WDS - optional)  
- **PowerShell (Optional)** – For automation & provisioning tasks  
- **Network Configuration** (DHCP, VLAN setup - optional for PXE)  

---

<h2>Tutorial</h2>

### **PXE Server Imaging Procedure**
**1. Prepare the Target Computers**  
- Connect computers to the network via Ethernet  
- Ensure VLAN access to the PXE server  

**2. Booting into PXE Mode**  
- Power on the computer and enter BIOS Setup (*varies by manufacturer*)  
- Navigate to **Startup Tab → Network Boot**  
- Ensure **LAN Boot** is enabled  

**3. PXE Boot Process**  
- Select **Network Boot** in BIOS  
- DHCP assigns IP address & provides PXE Boot Server details  
- PXE Boot Server connects with **TFTP Server** to retrieve boot files  

**4. Begin Imaging Process**  
- Follow company-specific imaging steps  
- Enter admin credentials to begin installation (**Prevents unauthorized imaging**)  
- Select appropriate image for the computer  
- Assign **Hostname & Active Directory Description** (if required)  

**5. Wait for Image Deployment to Complete**  

---

### **USB Drive Imaging Procedure**
**1. Create a Bootable USB Drive**  
- Use **company software library** to create bootable media  
- Select **"Create Task Sequence Media"** → **Bootable Media**  
- Secure USB with a **password**  

**2. Booting into USB Imaging Mode**  
- Insert **USB drive** into the computer  
- Access **BIOS Boot Menu** → Set **USB as the first boot device**  

**3. Begin Installation Process**  
- Follow installation steps for **system setup**  
- Apply **company-specific settings**  

---

<h2>References & Inspiration</h2>

- This repository was inspired by **best practices demonstrated** in the video  
  ["How to Image Computers | PXE | USB Drive"](https://www.youtube.com/watch?v=N9oohOcQI64) by East Charmer.  
- This documentation was structured based on **industry-standard imaging workflows**.  

---

<h2>Contributors</h2>

Maintained by **Victoria Deery**  

<h2>License</h2>

Open-source contribution guidelines apply—feel free to fork and improve!  
