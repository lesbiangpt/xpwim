# An introduction to WIM

Windows Imaging Format (WIM) is a file-based disk image format.

## How does it work?

A WIM file contains a set of files and associated filesystem metadata, however it is completely file-based.

WIM files are also able to contain multiple disk images, and can be split into multiple parts (SWM images).

WIM images can be made bootable, and the Windows bootloader supports booting from WIM files. Ever since Windows Vista, the installation environment boots from BOOT.WIM, which contains a specific version of Windows PE for Windows installation. The installation that will be deployed is stored inside of INSTALL.WIM.

Windows 8.1 and 10 introduced two ways to compress WIM images further.

## Tools

### ImageX

ImageX is a command-line tool to create, edit and deploy WIM images. Windows Vista RTM's version is included in the Windows Automated Installation Kit, however multiple Longhorn builds have specific ImageX versions for the WIM format they're using.

### DISM

Deployment Image Service and Management Tool (DISM) is a tool introduced in Windows 7 and Windows Server 2008 R2 that can perform more tasks than ImageX. ImageX was still required to capture images until it got deprecated and replaced fully by DISM in Windows 8.