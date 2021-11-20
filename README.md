# The Nameless Traveler
This is a Skyrim Wabbajack modlist.

If you're here because you installed the modlist, then read on for instructions on how to get some final configurations done.

# Preamble

You are free to fork this repository to make modifications and improve upon it.
No credit needs to be given, no nothing. Skyrim modding is a platform upon which to make the game your own.

At this early stage of development, the intent of the list is for you to download the list and try it out.

# Vision

This section documents the vision of this modlist. The Vision guides the development of the modlist.
You are free to change the vision if you fork it.

1. This modlist is aimed towards high-end PCs. I'm sorry, but the view from High Hrothgar and that Skyrim weather you've heard about won't look all that great on a potato PC. The target performance for this modlist is 30 fps at 2560x1080. Yes, that's right. The human eye can only see 24 fps anyway.

# Problems?

No support will be offered at this moment. As the development of the list is still in its early stages, it wouldn't make sense to try to fix things for now.

However, I will appreciate it if you could open a Github Issue documenting your issue. Perhaps the issue will be resolved naturally as development progresses. If not, I will make a patch for it after main development of the list is done.

# Installation

## System Requirements



## Requirements

### Skyrim Special Edition (SSE)

This modlist is currently built upon Skyrim Special Edition (SSE), **prior to the Anniversary Edition (AE) update**.
The mod author will not update this list to work with AE until certain [key mods](https://www.nexusmods.com/skyrimspecialedition/mods/32444) are updated to work with it as well.

If you are new to Skyrim, or new to modding, you may already have installed Anniversary Edition.
No worries, refer to [this section](#what-if-i-already-installed-anniversary-edition) for roll-back instructions.

## Pre-Installation

Before you install this modlist, before you even open Wabbajack, you should perform the following steps.

### Disabling Steam Overlay (Optional)

The Steam Overlay may cause issues with a heavily modded game. To disable it globally (for all your Steam games!), perform the following steps:
1. Open Steam.
2. In the toolbar at the top of the window, click Steam.
3. In the dropdown menu, click Settings.
4. Then in the popup box select the In-Game menu item.
5. Uncheck Enable the Steam overlay while in-game then click OK.

To disable it for just Skyrim Special Edition, perform the following steps:
1. Open Steam.
2. Click LIBRARY.
3. In your games list, look for The Elder Scrolls V: Skyrim Special Edition and right-click on it.
4. In the dropdown menu, click Properties.
5. Then, in the popup box, uncheck Enable the Steam Overlay while in-game.

### Disable Skyrim Updates ###

Bethesda updates Skyrim regularly to add Creation Club content. However, by doing so, it also prevents SKSE (an absolutely indispensible plugin) from working with the updated version until the devs update SKSE. In order to prevent Steam from updating these files, you are required to do the following:
1. In STEAM, right click on The Elder Scrolls V: Skyrim Special Edition.
2. In the menu that appears, click on Properties.
3. In the popup window, select the Updates tab.
4. In the selection box under "Automatic Updates", select "Only update this game when I launch it".
5. Close the window.

This makes it so that the game will only update if you launch it via Steam or by using the game launcher via MO2.
We will not be doing that, so this effectively prevents unwanted updates.

### Modifying Windows Page File ###

In order to prevent random Crash To Desktop (CTD) on region/cell transitions, perform the following:
1. Press Windows + R on your keyboard and enter sysdm.cpl ,3
2. Under the Performance section, press 'Settings'
3. Go to the Advanced tab at the top, and at the Virtual memory section press 'Change...'
4. Disable 'Automatically manage paging file size for all drives.
	1. If you have more than one drive, try enabling it for at least one more drive as a backup (make sure it has a decent bit of free space, like 15GB). Set the size to 'System managed size'.
	2. Otherwise, set a custom size for the drive it's currently on and increases the maximum size to be at least 20GB
	
### Full Range HDMI ###

Are you a lunatic that plays NSFW Skyrim on your 8K living room TV?
Or perhaps you spent everything on a PC powerful enough to run this modlist, but forgot to budget for a monitor upgrade?

If you connect your GPU to your display with a HDMI cable, you need to do the following:

**NVidia Users**

Go to your Nvidia Control Panel (right click on your desktop).
Then go to "change resolution" and find "Output Dynamic Range" and change it to "Full". (If it is greyed out press "Use NVIDIA color settings" first.)

**AMD Users**

If you're using a AMD/Radeon graphics card you need to do a similar tweak, but you have to change the display pixel format instead. This can be done by selecting "RGB 4:4:4 Pixel Format PC Standard (Full RGB)" instead of the default "RGB 4:4:4 Pixel Format Studio (Limited RGB)" inside of AMD Catalyst.

### What if I already installed Anniversary Edition??? ###

Well, tough luck buddy.

No, just kidding. Someone more talented than me made a [downgrade patcher](https://www.nexusmods.com/skyrimspecialedition/mods/57618).

Follow the instructions on the mod page to downgrade your game.

## Modding The Modlist

You can skip this section if you just want to play the list, and have no intention of making any changes to it.

If you do intend to change stuff around, you might want to install the following utilities.

-[**7-ZIP**](http://www.7-zip.org/download.html) - A free compression program. Effectively indispensible if you want to mod Skyrim.

-[**.NET 5.0 SDK**](https://dotnet.microsoft.com/download/dotnet/thank-you/sdk-5.0.403-windows-x64-installer) - Required for running Synthesis.

-[**MS Visual C++ Redistributable**](https://support.microsoft.com/en-gb/help/2977003/the-latest-supported-visual-c-downloads) - Required for running Synthesis.

-[**Creation Kit**](https://bethesda.net/en/game/bethesda-launcher) - The official tool for editing mods. You can use it to do almost anything. For the casual modder, it may be useful for converting legacy Skyrim (AKA oldrim) mods to work with SSE, within certain limitations.

-[**SSE Creation Kit Fixes**](https://www.nexusmods.com/skyrimspecialedition/mods/20061) - Various patches and bug fixes for the Creation Kit to make life easier.

### Anti-Virus Exceptions ###
Antivirus software and Windows Defender are known to interfere with Skyrim modding tools.

How to add a process exclusion to Window Defender:
1. Search for Virus & Threat Protection
2. Under Virus & Threat Protection Settings click Manage Settings.
3. Under Exclusions, click Add and Remove Exclusions.
4. Click the Add An Exclusion button.
5. From the drop-down menu click Process
6. In the popup window under Enter Process name add the file path to the .exe you wish to exclude.
7. For example, DynDOLODx64 on my system would be:J:\Skyrim Special Edition Tools\DynDOLOD Alpha 39\DynDOLODx64.exe
8. Repeat steps 4-6 for DynDOLODx64.exe, TexGenx64.exe, LODGenx64.exe, and Cathedral_Assets_Optimizer.exe. Do the same for the copies of Texconvx64.exe in your ...\DynDOLOD\Edit Scripts and ...\xLODGen\Edit Scripts folders.
9. Add a folder exclusion for your MO2 folder and your Tools folder(s). It's the same steps as above, but choose 'Folder' instead of 'Process'.
10. Add a file type exclusion for .nif

If you're a masochist who uses something like McAfee or Norton, you'll have to Google the instructions for them.

