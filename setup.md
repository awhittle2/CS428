# The Environment

Why are we using virtualization?
- Can run multipel operating systems simultaneously
- Easier software installations
- Testing and disaster recovery
- Infrastructure consolidation

Key terminology:
- Host OS: The operating system of the physical computer
- Guest OS: The operating system that is running inside the virtual machine
- Virtual machine (VM): The special environment that Oracle VM VirtualBox creates for your guest OS while it is running

## Downloading Virtualbox

System Requirements:
- 4GB of main memory***
- 2 CPU cores
- 80GB of free disk space***

(*** - needs updating once we know exactly how large of space we need)

### Windows Host OS
1. Please visit this site to: https://download.virtualbox.org/virtualbox/7.0.16/VirtualBox-7.0.16-162802-Win.exe
2. 

### Linux Host OS
Depending on what Linux distro you're host is running, your steps may be different. Please refer to https://www.virtualbox.org/wiki/Linux_Downloads for more information on the specifics on the different distros. For the purpose of this tutorial, the host OS will be Ubuntu 22.04.

1. Open the terminal
2. Type ```vim /etc/apt/sources.list```
3. Enter the following line in the file: ```deb [arch=amd64 signed-by=/usr/share/keyrings/oracle-virtualbox-2016.gpg] https://download.virtualbox.org/virtualbox/debian jammy contrib```
4. Download and register with: ```wget -O- https://www.virtualbox.org/download/oracle_vbox_2016.asc | sudo gpg --yes --output /usr/share/keyrings/oracle-virtualbox-2016.gpg --dearmor```
5. Ensure that your key fingerprint for oracle_vbox_2016.asc is ```B9F8 D658 297A F3EF C18D  5CDF A2F6 83C5 2980 AECF
Oracle Corporation (VirtualBox archive signing key) <info@virtualbox.org>```
    - If the signatures were invalid, enter the following commands:
    - ```sudo -s -H```
    - ```apt-get clean```
    - ```rm /var/lib/apt/lists/*```
    - ```rm /var/lib/apt/lists/partial/*```
    - ```apt-get clean```
    - ```apt-get update```
    - ```sudo apt-key remove 5CDFA2F683C52980AECF```
    - ```sudo apt-key remove D9C954422A4B98AB5139```
    - Continue on with the steps below
7. Update your system with: ```sudo apt-get update```
8. Install VirtualBox with: ```sudo apt-get install virtualbox-6.1```

## Downloading the Windows ISO
- https://www.microsoft.com/en-us/software-download/windows10
- Maybe: https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/

## Downloading the Remnux ISO
- https://docs.remnux.org/install-distro/get-virtual-appliance


-- Look into FLARE-VM: https://github.com/mandiant/flare-vm

## References
- https://www.sentinelone.com/labs/building-a-custom-malware-analysis-lab-environment/
- https://alexoloriz.com/building-a-malware-analysis-sandbox-a-step-by-step-guide/
