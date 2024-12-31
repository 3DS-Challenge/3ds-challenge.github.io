# EmuNAND Setup
To play any games made for the firmware used on the X1(A/B) units, the current solution involves setting up an EmuNAND.

## Prerequisites
* A modded 3DS
* An SD/microSD card of at least 2 GB that is ready for formatting
* The latest version of Luma3DS
* The latest version of GodMode9

## WARNING
This setup process will format your SD/microSD card, **ERASING everything present on it**. We recommend only using this with a blank card to prevent data loss.

## Instructions
1. Download the latest version of Luma3DS and extract it to your blank/ready-to-format SD card.
2. Download the latest version of GodMode9 and put it on your SD card inside the `/luma/payloads/` folder.
3. Insert the SD card into your system and hold Start + Power to open GodMode9.
4. Home button -> More... -> SD format menu
5. Select any EmuNAND size. RedNAND is recommended for smaller size (if the SD card is less than 4 GB, RedNAND size will be needed).
6. Set cluster size to auto when prompted.
7. Name the card anything or leave it as the default "GM9SD".
8. If prompted to clone SysNAND after formatting is complete, press B to select No.
9. Press R + Start to power off the system.
10. Insert the SD card into a computer. If prompted to format the SD card, ignore it.
11. Re-copy the latest version of Luma3DS to the SD card. Do NOT re-copy GodMode9 to the SD card.
12. Copy the contents of the EmuNAND Setup Kit to the root of the SD card.
13. Hold Start + Power again to open GodMode9.
14. Home Button -> More... -> Scripts -> `setup_emunand.gm9`
15. Follow the prompts on the bottom screen and, when prompted, press A to reboot the system.

Upon reboot, the system will load into the v243 prototype firmware with all prototype games present. The following games can be launched:
- CTAP: 3D Challenge / Face Ace debug build (Jul 7, 2010)
- NCAM: 3DS Camera Demo
- NGGF: Paper Mario 3DS Preview
- HID3: Control Test
- NFCE: Face Ace
- NSTG: Target Shooting
- NHCK: 3D Paddleball
- NPFD: Photo Dojo DX
- NHOP: 3D Hopper

The July 12, 2010 3D Challenge / Face Ace debug build is meant to be ran on a different firmware (v238) than the one the rest use (v243).
To run it, boot into GodMode9 and use the `firmware_switch.gm9` script to switch to the v238 firmware, reboot, then select 00000000 CTR-P-CTAP (JPN) in the menu. The other entries will not boot when in this menu. To switch back to the v243 firmware, boot into GodMode9 and run the `firmware_switch.gm9` script again.

To power off the system, hold the power button for about 10 seconds to force it to shut down.

To return to SysNAND, simply format or swap the SD card.


## Known Issues
* 3D does not work on New 3DS and later. This was unfortunately not fixable.
* Using the v243 firmware, gyro is too sensitive on 2DS and later.
* There are display issues in Target Shooting and Camera Demo on New 2DS XL systems.
* Using the v238 firmware, the circle pad appears to be calibrated incorrectly and does not work as intended.
* The v238 firmware does not work on New 3DS / New 3DS XL / New 2DS XL at the time of writing, so our script doesn't install it for these models. This is likely fixable, but requires in-depth debugging that is not possible at this time.
