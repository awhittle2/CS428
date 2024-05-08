# Virtualization Environment Setup Tutorial

## Table of Contents
1. [About Virtualization](#About-Virtualization)
2. [Downloading VirtualBox](#Downloading-VirtualBox)
3. [Downloading VMware](#Downloading-VMware)
4. [Downloading the Windows ISO](#Downloading-the-Windows-ISO)
5. [Downloading the Remnux ISO](#Downloading-the-Remnux-ISO)
6. [Setting Up the VMs](#Setting-Up-the-VMs)
7. [VM Networking](#VM-Networking)
8. [References](#References)

## About Virtualization
**Why Use Virtualization?**
- Run multiple operating systems concurrently on a single physical machine.
- Simplify software installations and deployments.
- Facilitate testing environments and disaster recovery.
- Optimize and consolidate computing infrastructure.

**Key Terminology:**
- **Host OS**: The operating system of the physical computer.
- **Guest OS**: The operating system running inside the virtual machine.
- **Virtual Machine (VM)**: A software-based emulation of a physical computer.

**System Requirements**:
- **Memory**: At least 4GB RAM
- **Processor**: 2 CPU cores
- **Disk Space**: Minimum 160GB of free space (preferably  256GB)
    - 75GB for FlareVM
    - 60GB for REMnux

## Downloading VirtualBox

### Installation Instructions:

#### For Windows Host OS
1. Visit [VirtualBox Downloads](https://download.virtualbox.org/virtualbox/7.0.16/VirtualBox-7.0.16-162802-Win.exe) to download the installer.
2. Run the downloaded executable and follow the on-screen instructions to install VirtualBox.

#### For Linux Host OS (Ubuntu 22.04)
#### GUI Version
1. Visit [VirtualBox Downloads](https://download.virtualbox.org/virtualbox/7.0.18/virtualbox-7.0_7.0.18-162988~Ubuntu~jammy_amd64.deb) to download the installer.
2. Run the download executable and follow the on-screen instructions to install VirtualBox.

#### Command Line Version
1. Open the terminal.
2. Add VirtualBox repository by editing the source list:
   ```bash
   echo "deb [arch=amd64 signed-by=/usr/share/keyrings/oracle-virtualbox-2016.gpg] https://download.virtualbox.org/virtualbox/debian jammy contrib" | sudo tee -a /etc/apt/sources.list
   ```
3. Download and add the Oracle VirtualBox signing key:
    ```bash
    wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo gpg --dearmor -o /usr/share/keyrings/oracle-virtualbox-2016.gpg
    ```
4. Update your package list and install VirtualBox:
    ```bash
    sudo apt-get update
    sudo apt-get install virtualbox-6.1
    ```

## Downloading VMWare

### Windows Host OS

### Linux Host OS

## Downloading the Windows ISO
1. Go to the [Windows Enterprise Landing Page](https://info.microsoft.com/ww-landing-windows-10-enterprise.html)
2. Enter in the required information under the "Register for your free trial today" section (first name, last name, email, company name, country/region, company size, job role, phone)
    - Note: It is recommended that you don't enter in your actual information as it is not verified by microsoft (including the phone number)
3. Click the download now button
4. Select the 64-bit edition under ISO
5. The download should start automatically

This link may work as well to [download the Windows ISO](https://go.microsoft.com/fwlink/p/?LinkID=2208844&clcid=0x409&culture=en-us&country=US)

## Downloading the REMnux OVA
### VMWare
1. Visit the [REMnux download documentition](https://docs.remnux.org/install-distro/get-virtual-appliance)
2. Under Step 1: Download the Virtual Appliance File click the link for Box
3. Press the download button

This link may work as well to [download the REMnux OVA for VMWare](https://app.box.com/s/l8uo6loohghdatius2f7icuyp14q3wp6)

### VirtualBox
1. Visit the [REMnux download documentition](https://docs.remnux.org/install-distro/get-virtual-appliance)
2. Under Step 1: Download the Virtual Appliance File click the "VirtualBox OVA" tab
3. Click the link to box
4. Press the download button

This link may work as well to [download the REMnux OVA for VirtualBox](https://app.box.com/s/8matvs5l0gc8vkr4xfq3szdm7mc9o0ad)

## Setting Up the VMs
### Virtualbox

### VMWare


## VM Networking
### Virtualbox

### VMWare


-- Look into FLARE-VM: https://github.com/mandiant/flare-vm

## References
- https://www.sentinelone.com/labs/building-a-custom-malware-analysis-lab-environment/
- https://alexoloriz.com/building-a-malware-analysis-sandbox-a-step-by-step-guide/
