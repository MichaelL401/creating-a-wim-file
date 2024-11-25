Documentation of creating a Windows Imaging Format (WIM) file from a live Windows system. This will be useful for  deploying consistent configurations across multiple systems.

## Prerequisites

- A preconfigured machine with **Windows 10** installed.
- Drivers, required software, and user accounts already configured on the system.
- A bootable **Windows 10 installation USB** to access the Windows Preinstallation Environment (Windows PE).
- Administrator privileges on the system.

---

## Steps to Create a WIM File
(This was already complete before the beginning of the project)

## 1. Install and Configure the System
1. Install **Windows 10** on the target machine.
2. Install all necessary hardware drivers.
3. Set up required software, user accounts, and system configurations.
---

##  Boot into Windows PE
Insert the Windows 10 installation USB and boot the machine from the USB drive.
Use Shift + F10 to open a command prompt within the Windows Preinstallation Environment.
---


##  Optimize and Capture the Image 
 Optimize the system image:
```
DISM /image:C:\ /optimize-image /boot
```
Prepares the image for capture and ensures it is optimized for bootable deployment.

Capture the image: 
```
Dism /Capture-Image /ImageFile:"C:\image.wim" /CaptureDir:C:\ /Name:image
```
```
/ImageFile: The destination path and filename for the WIM file.
/CaptureDir: Specifies the root directory to capture (typically C:\).
/Name: The name assigned to the captured image in the WIM file.
```
---

## Verify the WIM File
Reboot the system and log in.
Confirm the WIM file exists at the specified destination (e.g., C:\image.wim).
---

## Use Cases
Deploy the WIM file to other machines for consistent system configurations
---

## Sources
- [Sysprep: Generalize a Windows Installation](https://learn.microsoft.com/en-us/windows-hardware/manufacture/desktop/sysprep--generalize--a-windows-installation?view=windows-11)  
- [Capture and Apply Windows Using a Single WIM](https://learn.microsoft.com/en-us/windows-hardware/manufacture/desktop/capture-and-apply-windows-using-a-single-wim?view=windows-11)  



