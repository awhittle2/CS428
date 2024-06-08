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
### For Windows Host OS
1. Visit [VirtualBox Downloads](https://download.virtualbox.org/virtualbox/7.0.16/VirtualBox-7.0.16-162802-Win.exe) to download the installer.
2. Run the downloaded executable and follow the on-screen instructions to install VirtualBox.

### For Linux Host OS (Ubuntu 22.04)
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
### VirtualBox
1. Visit the [REMnux download documentition](https://docs.remnux.org/install-distro/get-virtual-appliance)
2. Under Step 1: Download the Virtual Appliance File click the "VirtualBox OVA" tab
3. Click the link to box
4. Press the download button

This link may work as well to [download the REMnux OVA for VirtualBox](https://app.box.com/s/8matvs5l0gc8vkr4xfq3szdm7mc9o0ad)

### VMWare
1. Visit the [REMnux download documentition](https://docs.remnux.org/install-distro/get-virtual-appliance)
2. Under Step 1: Download the Virtual Appliance File click the link for Box
3. Press the download button

This link may work as well to [download the REMnux OVA for VMWare](https://app.box.com/s/l8uo6loohghdatius2f7icuyp14q3wp6)

## Setting Up the VMs - VMWare

### Creating the Windows ISO
1. Accept the applicable notices and license terms
![windows-iso-screenshot](./images/pre-windows-1.png)
2. Select "Create installation media (USB flash drive, DVD, or ISO file) for another PC" and press next
![windows-iso-screenshot](./images/pre-windows-2.png)
3. If selected, unselect the "Use the recommended options for this PC" box. Ensure that the language is english, the edition is Windows 10, the architecture is 64-bit, and press next
![windows-iso-screenshot](./images/pre-windows-3.png)
4. Select "ISO file" and press next
![windows-iso-screenshot](./images/pre-windows-4.png)
5. Wait for the "Downloading Windows 10" page
![windows-iso-screenshot](./images/pre-windows-5.png)
6. Wait for the "Creating Windows 10 media" page
![windows-iso-screenshot](./images/pre-windows-6.png)
7. Press finish
![windows-iso-screenshot](./images/pre-windows-7.png)

### Installing Flare VM
1. In VMWare Workstation, select "Create a New Virtual Machine"
![windows-screenshot](./images/windows-1.png)
2. Ensure that "Typical (recommended)" is selected and press next
![windows-screenshot](./images/windows-2.png)
3. Select "Installer disc image file (iso):" and press "Browse..."
![windows-screenshot](./images/windows-3.png)
4. Find the ISO image you just created, select open, and then next
![windows-screenshot](./images/windows-4.png)
5. Press next
![windows-screenshot](./images/windows-5.png)
6. Ensure "Maximum disk size (GB):" is 60.0, "Split virtual disk into multiple files" is selected, and press next
![windows-screenshot](./images/windows-6.png)
7. Press finish
![windows-screenshot](./images/windows-7.png)
8. Upon the "Press any key to boot from CD or DVD..." screen, press a key to continue
![windows-screenshot](./images/windows-8.png)
9. Wait for bootup
![windows-screenshot](./images/windows-9.png)
10. On the "Windows Setup" page, ensure that "English" is selected for language to install and time and currency format, "US" is selected for keyboard or input method, and press next
![windows-screenshot](./images/windows-10.png)
11. On the "Activate Windows" screen, select "I don't have a product key", and press next
![windows-screenshot](./images/windows-11.png)
12. On the "Select the operating system you want to install" screen, select "Windows 10 Pro", and press next
![windows-screenshot](./images/windows-12.png)
13. On the "Applicable notices and license terms" screen, check "I accept the license terms", and press next
![windows-screenshot](./images/windows-13.png)
14. On the "Which type of installation do you want?" screen, select "Custom: Install Windows only (advanced)"
![windows-screenshot](./images/windows-14.png)
15. On the "Where do you want to install Windows?" screen, select "Drive 0 Unallocated Space", and press next
![windows-screenshot](./images/windows-15.png)
16. Wait for the installation
![windows-screenshot](./images/windows-16.png)
17. On the "Let's start with region. Is this right?" screen, select "United States", and press yes
![windows-screenshot](./images/windows-17.png)
18. On the "Is this the right keyboard layout?" screen, select "US", and press yes
![windows-screenshot](./images/windows-18.png)
19. On the "Want to add a second keyboard layout?" screen, press skip
![windows-screenshot](./images/windows-19.png)
20. Wait for some more installation
![windows-screenshot](./images/windows-20.png)
21. On the "How would you like to set up?" screen, select "Set up for personal use", and press next
![windows-screenshot](./images/windows-21.png)
22. On the "Let's add your account" screen, select "Offline account"
![windows-screenshot](./images/windows-22.png)
23. On the "Sign in to enjoy the full range of Microsoft apps and services" screen, select "Limited experience"
![windows-screenshot](./images/windows-23.png)
24. On the "Who's going to use this PC?" screen, type "Malware-Box" (or whatever you want your username to be), and press next
![windows-screenshot](./images/windows-24.png)
25. On the "Always have access to your recent browsing data" screen, press not now
![windows-screenshot](./images/windows-25.png)
26. On the "Choose privacy settings for your device" screen, unselect Location, Diagnostic data, Tailored experiences, Find my device, Inking & typing, and Advertising ID, and press accept
![windows-screenshot](./images/windows-26.png)
27. On the "Let's customize your experience" screen, press skip
![windows-screenshot](./images/windows-27.png)
28. On the "Let Cortana help you get things done" screen, press not now
![windows-screenshot](./images/windows-28.png)
29. Wait for final Windows installation
![windows-screenshot](./images/windows-29.png)
30. In the taskbar, search for "Proxy Settings", and open it
![windows-screenshot](./images/windows-30.png)
31. Under "Automatic proxy setup", unselect "Automatically detect settings", and close the window
![windows-screenshot](./images/windows-31.png)
32. In the taskbar, search for "Windows Security", and open it
![windows-screenshot](./images/windows-32.png)
33. Press "Virus & threat protection" and "Manage settings" under "Virus & threat protection settings"
![windows-screenshot](./images/windows-33.png)
34. On the "Virus & threat protection settings", unselect "Real-time protection" and "Cloud-delivered protection"
![windows-screenshot](./images/windows-34.png)
35. Also Unselect "Automatic sample submission" and "Tamper Protection", then close the window
![windows-screenshot](./images/windows-35.png)
36. 
![windows-screenshot](./images/windows-36.png)
37. In the taskbar, search for "Edit group policy"
![windows-screenshot](./images/windows-37.png)
38. 
![windows-screenshot](./images/windows-38.png)
39. In the Local Group Policy Editor, click on the "Administrative Templates" and the "Windows Components" folders
![windows-screenshot](./images/windows-39.png)
40. Scroll down until you find the "Microsoft Defender Antivirus" folder, click on it, and double click the "Turn off Microsoft Defender Antivirus" setting
![windows-screenshot](./images/windows-40.png)
41. Select enabled for the setting, then press apply and ok
![windows-screenshot](./images/windows-41.png)
42. Under the "Administrative Templates" folder, click on "Network", "Network Connections", and "Windows Defender Firewall" folders
![windows-screenshot](./images/windows-42.png)
43. Click the "Domain Profile" folder and double click the "Windows Defender Firewall: Protect all network connections" setting
![windows-screenshot](./images/windows-43.png)
44. Select disabled for the setting, then press apply and ok
![windows-screenshot](./images/windows-44.png)
45. Click the "Standard Profile" in the same path as before and double click the "Windows Defender Firewall: Protect all network connections" setting
![windows-screenshot](./images/windows-45.png)
46. Select disabled for the setting, then press apply and ok
![windows-screenshot](./images/windows-46.png)
47. Close the window, go back to the desktop, and select the "Take a snapshot of this virtual machine" button within VMware
![windows-screenshot](./images/windows-47.png)
48. Under the description, type "Pre-FlareVm", then press take snapshot
![windows-screenshot](./images/windows-48.png)
49. In the taskbar, search for "Powershell", and run it as an administrator
![windows-screenshot](./images/windows-49.png)
50. Type `cd C:\Users\Malware-Box\Desktop\`
- Note: The command will be different if your username is different
![windows-screenshot](./images/windows-50.png)
51. Type `(New-Object net.webclient).DownloadFile('https://raw.githubusercontent.com/mandiant/flare-vm/main/install.ps1',"$([Environment]::GetFolderPath("Desktop"))\\install.ps1")`
![windows-screenshot](./images/windows-51.png)
52. Ensure that install.ps1 appeared on your desktop and type `Unblock-File .\install.ps1`
![windows-screenshot](./images/windows-52.png)
53. Type `Set-ExecutionPolicy Unrestricted`
![windows-screenshot](./images/windows-53.png)
54. Type `Y` for the yes option
![windows-screenshot](./images/windows-54.png)
55. If there are no errors, the script will ask "Have you taken a VM snapshot to ensure you can revert to pre-installation state? (Y/N):". Type `Y`
![windows-screenshot](./images/windows-55.png)
56. Enter in the credentials you chose, if you did not enter a password, press enter
![windows-screenshot](./images/windows-56.png)
57. Wait for initial installation of flare vm
![windows-screenshot](./images/windows-57.png)
58. Once on the "FLARE VM Install Customization" screen, press ok
![windows-screenshot](./images/windows-58.png)
59. Wait for flare vm installation
![windows-screenshot](./images/windows-59.png)
60. If prompted for "Autologon Password", enter the password you chose, if you did not enter a password, press enter
![windows-screenshot](./images/windows-60.png)
61. Wait for this process to finish. It should take a while, but in the meantime, you can get started on the REMnux VM

### Setting Up REMnux
1. In VMware, click file and then open
![remnux-screenshot](./images/remnux-1.png)
2. Browse to where you install the remnux ova and press open
![remnux-screenshot](./images/remnux-2.png)
3. Type "Remnux" under "Name for the new virtual machine:" and press import
![remnux-screenshot](./images/remnux-3.png)
4. Wait for it to be imported
![remnux-screenshot](./images/remnux-4.png)
5. Click the green play button to power on the virtual machine
![remnux-screenshot](./images/remnux-5.png)
6. Wait for everything to load
![remnux-screenshot](./images/remnux-6.png)
7. Type `remnux upgrade` in the terminal that should have automatically opened
![remnux-screenshot](./images/remnux-7.png)
8. Wait for the upgrade to finish
![remnux-screenshot](./images/remnux-8.png)
9. Click edit and then "Virtual Network Editor" in VMware
![remnux-screenshot](./images/remnux-9.png)
10. Press "Change Settings" if applicable
![remnux-screenshot](./images/remnux-10.png)
11. Press the "Add Network..." button
![remnux-screenshot](./images/remnux-11.png)
12. Select an unused VMnet number under "Select a network to add" and press ok
![remnux-screenshot](./images/remnux-12.png)
13. Click on the new VMnet network you made, then select "Host-only", unselect "Connect a host virtual adapter to this network", take note of the subnet IP, and press ok
![remnux-screenshot](./images/remnux-13.png)
14. Click the dropdown next to the pause button and click "Restart Guest" in VMware
![remnux-screenshot](./images/remnux-14.png)
15. In the prompt, press shut down
![remnux-screenshot](./images/remnux-15.png)
16. Right click on the remnux machine you made in VMware
![remnux-screenshot](./images/remnux-16.png)
17. Press the settings option at the bottom
![remnux-screenshot](./images/remnux-17.png)
18. Click on "Network Adapter" and change the network connection to have "Custom" selected, then select the VMnet you created, and press ok
![remnux-screenshot](./images/remnux-18.png)
19. Press the green play button to power on the virtual machine again
![remnux-screenshot](./images/remnux-19.png)
20. Type `ip a` in the termnial and ensure that your ip address matches the VMnet subnet IP you took note of in step 13
![remnux-screenshot](./images/remnux-20.png)
21. Type `cd /etc/inetsim` and `sudo nano inetsim.conf`
![remnux-screenshot](./images/remnux-21.png)
22. In the file, uncomment the line "start_service dns"
![remnux-screenshot](./images/remnux-22.png)
23. Uncomment the line "service_bind_address" and put the address as "0.0.0.0"
![remnux-screenshot](./images/remnux-23.png)
24. Uncomment the line "dns_default_ip" and put the address as the static ip you want to use for remnux, then save and exit out of the file
![remnux-screenshot](./images/remnux-24.png)
25. Type `cd /etc/netplan/` and `sudo nano 01-netcfg.yaml`
![remnux-screenshot](./images/remnux-25.png)
26. Under the line "dhcp4", change it to "no" and add an "addresses: [ <ip address>/subnet ]" line under it. For the ip address, enter the static ip you want to use for remnux, then save and exit out of the file
![remnux-screenshot](./images/remnux-26.png)
27. Type `sudo reboot now` and wait for the reboot to finish
![remnux-screenshot](./images/remnux-27.png)

### Final Touches
1. Make sure everything was installed correctly by looking at log.txt, then exit out
![flarevm-screenshot](./images/flare-0.png)
2. In the bottom right, click the network icon and press "Network & Internet settings" option
![flarevm-screenshot](./images/flare-1.png)
3. Press the "properties" option under "Ethernet0"
![flarevm-screenshot](./images/flare-2.png)
4. Click "Ethernet 0" on the "Network Connections" page
![flarevm-screenshot](./images/flare-3.png)
5. Press "Properties" on the "Ethernet0 Status" page
![flarevm-screenshot](./images/flare-4.png)
6. Find the option labeled "Internet Protocol Version 4 (TCP/IPv4)" and press "Properties"
![flarevm-screenshot](./images/flare-5.png)
7. Under "Use the following IP address" option, type the IP address you want for FlareVM and "255.255.255.0" as the subnet mask. Then under "Use the following DNS server addresses" option, type the IP address you used for REMNux VM. Press ok to save the changes
![flarevm-screenshot](./images/flare-6.png)
8. Type ipconfig to make sure your changes was successful and that the IP address matches what you put in the last step. If it is not successful, make sure to follow steps 9 and 10
![flarevm-screenshot](./images/flare-7.png)
9. In VMware, right click the WIndows VM and select "Settings..."
![flarevm-screenshot](./images/flare-8.png)
10. Make sure that the virtual network is set to VMnet2 or whatever the network you setup for REMnux
![flarevm-screenshot](./images/flare-9.png)
11. To make sure the network is correctly set up, try pinging the IP address of REMnux. If it is unsuccessful look at the network settings or restart the VM
![flarevm-screenshot](./images/flare-10.png)
12. To make sure the network is correctly set up on the REMnux side, try pinging the IP address of FlareVM
![flarevm-screenshot](./images/remnux-after-flare-10.png)
13. In VMware, select the "Take a snapshot of this virtual machine" button on FlareVM
![flarevm-screenshot](./images/flare11.png)
14. Enter in a relevant description for the snapshot and press "Take Snapshot"
![flarevm-screenshot](./images/flare-12.png)
15. In VMware, select the "Take a snapshot of this vritual machine" button on REMnux
![flarevm-screenshot](./images/remux-after-flare-12.png)
16. Enter in a relevant description for the snapshot and press "Take Snapshot"
![flarevm-screenshot](./images/remnux-after-flare-12-2.png)
17. Shut down both VMs, select the Windows 10 machine/FlareVM, and press file in the top left
![flarevm-screenshot](./images/export-1.png)
18. In the settings, press "Export to OVF..."
![flarevm-screenshot](./images/export-2.png)
19. Save the file
![flarevm-screenshot](./images/export-3.png)
20. Wait for the export
![flarevm-screenshot](./images/export-4.png)
21. Then, select the REMnux VM and press file in the top left
![flarevm-screenshot](./images/export-5.png)
22. In the file settings, press "Export to OVF..."
![flarevm-screenshot](./images/export-6.png)
23. Save the file and wait for the export to finish
![flarevm-screenshot](./images/export-7.png)

Note: Please note that while OVF is not the same as OVA, VMware has a tool to change OVFs to OVAs. Follow this tutorial to help figure out the process: https://www.vmwarearena.com/convert-ova-to-ovf-using-the-vmware-ovf-tool/

### Importing OVAs
1. In VMware, press file in the top left, and press "Open..."
![flarevm-screenshot](./images/export-8.png)
2. Find the file, and select open. VMware should automatically start the import process
![flarevm-screenshot](./images/export-9.png)

To view the exports we created, please refer to this link: https://oregonstate.box.com/s/b3npz71fuxbuhyhz8q9xfzq1d6zwvitm

## References
- https://www.sentinelone.com/labs/building-a-custom-malware-analysis-lab-environment/
- https://alexoloriz.com/building-a-malware-analysis-sandbox-a-step-by-step-guide/
