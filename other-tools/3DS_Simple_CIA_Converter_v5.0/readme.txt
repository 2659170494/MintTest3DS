3DS Simple CIA Converter by RikuKH3
-----------------------------------

After looking at how unnecessarily complicated current CIA converting methods are, I decided to write
this tool. It's very simple and doesn't use Python or .NET Framework or any other programs and scripts,
just my own code.

I decided to take slightly different approach to keep things simple and only use ExHeader XORpads. They are
1MB each in size and multiple ROM files supported during 'ncchinfo.bin' creation, so you can make xorpads for a
bunch of games in one go. With version 4.0 I added ability to patch minimum required kernel version (FW Spoof)
and 'RegionFree', which requires *.exefs_norm.xorpad's. 'FW Spoof' function checks FW version game requires to
run and only applied if original value exceeds entered (2D02:FW8.0-8.1, 2E02:FW9.0-9.2, 3002:FW9.3, 3102:FW9.5, 3202:FW9.6-9.8).

1) Put your 3DS games into 'roms' folder and press 'Create ncchinfo.bin file' button to create 'ncchinfo.bin'
from 3DS ROMs.

2) Use GodMode9 along with created 'ncchinfo.bin' to generate ExHeader XORpads, put it in root of SD card,
launch GodMode9 and follow '[0:] SDCARD --> nccginfo.bin --> NCCHinfo options... --> Build XORpads (SD output)'.

3) Put *.xorpad files you generated on 3DS from SD root into 'xorpads' folder, press 'Convert 3DS ROM to CIA'
button, select folder with *.3ds files and wait for program to finish.

With version 5.0 of the program XORpads are no longer required if proper 'boot9.bin' file detected in the same folder.
To generate 'boot9.bin' file you need B9S hack installed on your 3DS. Just hold (Start) + (Select) + (X) on boot and
it will be saved to the /boot9strap/ folder on your SD card.

Version 5.0, 2017-09-24
-----------------------
- Added KeyX extraction from 'boot9.bin' file, no xorpad required if proper key provided.

Version 4.3, 2015-07-03
-----------------------
- Added zero-key encrypted ROM support, no xorpad required.
- Added error skip so program doesn't stop converting remain files.
- Added application Major version writing into TMD.

Version 4.0, 2015-06-28
-----------------------
-  Added Download Play support.
-  Added input 3DS ROM folder selection dialog.
-  Added searching for *.3ds|*.3dz files in subfolders.
-  Improved partition type detection.
-  Improved 'FW Spoof' function.
-  Set RegionFree to default without ability to disable it.
-  Code cleanup and minor optimizations.
