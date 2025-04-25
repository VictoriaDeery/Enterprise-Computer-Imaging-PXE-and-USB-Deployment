<p align="center">
<img img width="260" alt="image" src="https://tse1.mm.bing.net/th/id/OIG3.ZsRTSLeL1.qmcEDs1Tb.?pid=ImgGn" alt="Enterprise Computer Imaging"/>
</p>

<h1><b>Enterprise Computer Imaging - PXE & USB Deployment</b></h1>

<h2>Overview</h2>

This repository provides a detailed guide on imaging computers using **PXE servers** and **USB drives**. It covers **enterprise provisioning techniques**, **network-based mass imaging**, and **manual deployment workflows**. Optional sections explore **DHCP configurations**, **PowerShell scripting**, and **Active Directory (AD) integration** for IT professionals.



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
**Overview:PXE Boot Workflow** 
- Client machine boots from network
- DHCP process (Broadcast, Offer, Request, Acknowledge) assigns an IP address and provides PXE boot server details
- Client connects to TFTP server and requests the boot file
- TFTP server sends the boot file, which the client loads into memory
- Once loaded, imaging or OS installation process starts

**1. Prepare the Target Computers**  
- Connect computers to the network via Ethernet  
- Ensure correct VLAN access to the PXE server  

**2. Booting into PXE Mode**  
- Power on the computer and enter BIOS Setup (*varies by manufacturer, search online*)  
- Navigate to **Startup Tab > Network Boot**  
- Ensure **LAN Boot** is enabled. 

**3. PXE Boot Process**  
- Select **Network Boot** in BIOS, or relevant selection to connect to the network.  
- DHCP assigns IP address & provides PXE Boot Server details  
- PXE Boot Server connects with **TFTP Server** to retrieve boot files
- The client should now display "Entering Network Boot..."   

**4. Begin Imaging Process**  
- Follow company-specific imaging steps  
- Enter admin credentials (**password**) to begin installation (this **Prevents unauthorized imaging**)  
- Select appropriate image for the computer  
- Assign **Hostname & Active Directory Description** (potentially optional as it is for record-keeping and organization)  

**5. Wait for Image Deployment to Complete**  

---

### **USB Drive Imaging Procedure**
**OVERVIEW: USB Boot Workflow**
- Insert USB drive into the computer
- Access BIOS Boot Menu → Set USB as the first boot device
- System loads installation media
- Begin imaging or OS installation

**1. Create a Bootable USB Drive**  
- Potentially use **company software library** to create bootable media  
- Select **"Create Task Sequence Media" > Bootable Media > Next > Removable USB Drive**  
- Secure USB with a **password**
- If the company protocol is to have an expiration for the bootable media, select that now.

**2. Booting into USB Imaging Mode**  
- Insert **USB drive** into the computer  
- Access **BIOS Boot Menu** > Set **USB as the first boot device**
  - This can be done by using the appropriate function buttons (see #2 above) or manually by opening the **BIOS Settings > Boot Order Options > Change First Boot Order to USB > Save Changes and Exit BIOS.**
-   The computer will reboot and load the image.

**3. Begin Installation Process**  
- Follow installation steps for **system setup**  
- Apply **company-specific settings**  

---

<h2>References & Inspiration</h2>

- This repository was inspired by **best practices demonstrated** in the video  
  ["How to Image Computers | PXE | USB Drive"](https://www.youtube.com/watch?v=N9oohOcQI64) by East Charmer.  
- This documentation was structured based on **industry-standard imaging workflows**.  
