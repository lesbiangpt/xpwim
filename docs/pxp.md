# PantherXP
PantherXP is a WIM repacking method for Windows XP that automates the repack process and relies on the Panther Deployment engine (version 6.0.4053.0).
## Important information before starting
- This is a legacy method, meaning this will be soon replaced by a better method (we will keep this in our documentation though!)
- You might have to disable your antivirus before starting
## Requirements
- A hypervisor (Hyper-V, VMware Workstation Pro, VMware Workstation Player, Oracle VM Virtualbox, QEMU)
- A Windows XP ISO
- [PantherXP](https://web.archive.org/web/20160201185504/http://thuun.boot-land.net/PantherXP/files/pantherxp_en_dk.exe)
- OSFMount
- Any software that can open the contents of an ISO (we recommend 7-Zip)
## Part one: Preparing the ISO
1. Run the PantherXP executable and extract the files where you wish
2. Open the ISO with 7-zip and extract its contents in another folder
3. From the PantherXP folder, copy the `legacy_boot.cmd` file to the root of the extracted ISO
4. Run the `legacy_boot.cmd` file in the extracted ISO root
5. Copy the `[BOOT]` folder to `where you extracted PantherXP in\legacy_template\[ROOT]`
6. Copy the `i386` folder to `where you extracted PantherXP in\legacy_template\[ROOT]\sources\Dist`
7. Replace every file that is 0KB in size with their original versions from the ISO. This is because of a flaw in the PantherXP process.
8. On the `where you extracted PantherXP in\legacy_template\[ROOT]\boot` folder, edit `WINNT.SIF` and replace the following:
 - Product key (put in the product key of the ISO you got)
 - OrgName
9. Then, in `where you extracted PantherXP in\legacy_template\[ROOT]\sources\Dist\$OEM$\$1\sysprep\` folder, edit `sysprep.inf`. Yet again, edit the following:
 - Product key
 - OrgName
10. Now head over to `where you extracted PantherXP in\build\`, and run `legacy_cdimage.cmd`. It'll now build the ISO. This is NOT based on .wim yet.
## Part two: Capturing the image to WIM
TBD