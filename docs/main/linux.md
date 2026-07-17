---
sidebar_position: 6
title: Linux Instructions
hide_title: true
sidebar_label: Linux Instructions
---

# <p align="center"> <img width="546" height="60" alt="importantnotices" src="https://github.com/user-attachments/assets/cfc2f45d-d0c9-484a-94b3-265e538757f9" /> </p>

:::danger Important
This guide assumes you are installing on the same drive that your distro is installed to.

At the time of writing, this guide only covers installing for the Steam version of Fallout: New Vegas and not for GOG or Epic versions, but instructions for those platforms are planned.
Terminal commands are provided for those who prefer it over using graphical methods. If you are not using the terminal for this, make sure your preferred file explorer has Show Hidden Files enabled.
lsfg-vk does not work for this setup at this time.
:::

# <p align="center"> <img width="546" height="60" alt="prerequisites" src="https://github.com/user-attachments/assets/2b91127c-dbbd-48b2-b91b-c556a68adc13" /> </p>

FNV 4GB Patcher for Linux
https://www.nexusmods.com/newvegas/mods/62552?tab=files

Jackify (Linux version of Wabbajack)
https://github.com/Omni-guides/Jackify/releases !! Download the file under Assets that says Jackify.AppImage and not Source code !!

TTW
https://mod.pub/ttw/133-tale-of-two-wastelands

### <p align="center"> <img width="546" height="60" alt="creatingnecessaryfilepaths" src="https://github.com/user-attachments/assets/6db84a3d-8707-4a17-9c8f-0db14826481c" /> </p>

- Open a terminal and run
- mkdir ~/NuclearSunset ~/NuclearSunset/downloads
- This will create a folder called NuclearSunset in your home folder and a nested downloads folder in it. If you're installing to a different mounted drive, create your folders there instead.
- Move Jackify.AppImage to ~/NuclearSunset.
<br></br>
<br></br>

### <p align="center"> <img width="546" height="60" alt="creatingcleaninstallsandbackups" src="https://github.com/user-attachments/assets/3a620e09-ee91-4608-bfa2-595f7d414703" /> </p>

- Navigate to your path where Fallout New Vegas is installed to and rename Fallout New Vegas to something different like FNVBackup.
    - Native Steam: mv ~/.local/share/Steam/steamapps/common/Fallout\ New\ Vegas/ ~/.local/share/Steam/steamapps/common/FNVBackup
    - Flatpak Steam: mv ~/.var/app/com.valvesoftware.Steam/data/Steam/steamapps/common/Fallout\ New\ Vegas/ ~/.var/app/com.valvesoftware.Steam/data/Steam/steamapps/common/FNVBackup
- Navigate to your compatdata folder, find 22380 and rename it to 22380-backup
    - Native Steam: mv ~/.local/share/Steam/steamapps/compatdata/22380 ~/.local/share/Steam/steamapps/compatdata/22380-backup
    - Flatpak Steam: mv ~/.var/app/com.valvesoftware.Steam/data/Steam/steamapps/compatdata/22380 ~/.var/app/com.valvesoftware.Steam/data/Steam/steamapps/compatdata/22380-backup
- Uninstall Fallout New Vegas and Fallout 3 from Steam.
- Reinstall Fallout New Vegas and Fallout 3.
<br></br>
<br></br>

### <p align="center"> <img width="546" height="60" alt="generating fresh ini files" src="https://github.com/user-attachments/assets/b0ee1420-0a57-4b58-b49f-5bfad94cfa58" /> </p>

- Launch Fallout: New Vegas from Steam
- Press OK when the Detecting Video Hardware popup appears.
- Close the launcher.
- Repeat for Fallout 3.
<br></br>
<br></br>

### <p align="center"> <img width="546" height="60" alt="installingnuclearsunset" src="https://github.com/user-attachments/assets/b06987f9-401b-4a31-98ab-5546cceb67f8" /> </p>

- Open a terminal and run the following command.
`chmod +x ~/NuclearSunset/Jackify.AppImage & ./Jackify.AppImage`

- Open the settings page and log into your Nexus account.
- Close the settings page and click Modlist Tasks, and select Install a Modlist (Automated)
- Set Game Type: to Fallout: New Vegas and set Modlist: to Nuclear Sunset.
- In Install Directory, select your NuclearSunset folder.
- In Downloads Directory navigate to your NuclearSunset folder and select downloads.
- Select Start Installation
:::warning
This process will usually take at least half an hour to finish 
:::
<br></br>
<br></br>

### <p align="center"> <img width="546" height="60" alt="creatingacleanstocknewvegasfolder" src="https://github.com/user-attachments/assets/d986fd93-5533-4717-aaeb-fca2f9433f5c" /> </p>

- Navigate to the newly reinstalled New Vegas folder and copy ALL files from the folder to ~/NuclearSunset/[NoDelete] \Stock \New \Vegas
    - Native: cp ~/.local/share/Steam/steamapps/common/Fallout\ New\ Vegas/* ~/NuclearSunset/[NoDelete]\ Stock\ New\ Vegas/
    - Flatpak: cp ~/.var/app/com.valvesoftware.Steam/data/Steam/steamapps/common/Fallout\ New\ Vegas/* ~/NuclearSunset/[NoDelete]\ Stock\ New\ Vegas/
:::danger Important
- You need to remove d3d9.dll from [NoDelete] Stock New Vegas. This is not an optional step. This is from the DXVK mod and is not needed as Linux already uses DXVK natively. If you do not remove this, you will crash any time you leave an interior.
 `rm ~/NuclearSunset/[NoDelete]\ Stock\ New\ Vegas/d3d9.dll ~/NuclearSunset/[NoDelete]\ Stock\ New\ Vegas/dxvk.conf`
 :::

:::tip
If you made a backup of Fallout New Vegas as mentioned before, you can place your old folder (FNVBackup) back into `/path/to/Steam/steamapps/common/`
  - Native Steam:
    `cp -fR ~/.local/share/Steam/steamapps/common/FNVBackup/* ~/.local/share/Steam/steamapps/common/Fallout\ New\ Vegas/`
    `cd ~/.local/share/Steam/steamapps/compatdata`
    `rm -rf ~/.local/share/Steam/steamapps/compatdata/22380 && mv ~/.local/share/Steam/steamapps/compatdata/22380-backup/* ~/.local/share/Steam/steamapps/compatdata/22380`
  - Flatpak Steam:
    `cd ~/.var/app/com.valvesoftware.Steam/data/Steam/steamapps/common`
    `cp -fR ~/.var/app/com.valvesoftware.Steam/data/Steam/steamapps/common/NVBackup/* ~/.var/app/com.valvesoftware.Steam/data/Steam/steamapps/common/Fallout\ New\ Vegas/`
    `cd ~/.var/app/com.valvesoftware.Steam/data/Steam/steamapps/compatdata`
    `rm -rf ~/.var/app/com.valvesoftware.Steam/data/Steam/steamapps/compatdata/22380 && mv ~/.var/app/com.valvesoftware.Steam/data/Steam/steamapps/compatdata/22380-backup/* ~/.var/app/com.valvesoftware.Steam/data/Steam/steamapps/compatdata/22380`
:::
<br></br>
<br></br>

### <p align="center"> <img width="546" height="60" alt="launching mod organizer 2 (mo2)" src="https://github.com/user-attachments/assets/971f42eb-20ec-4de7-84ba-aeba449e681e" /> </p>

- Open Steam, find Nuclear Sunset in your games list, and launch it.
- Jackify should have created this entry for you. If not, add it through Add a Game in the bottom left, Add a Non-Steam Game, then select Browse in the bottom left of the new window. Navigate to your Nuclear Sunset folder, and select ModOrganizer.exe then select Add Selected Progams.
- Right click on the entry in your games list and select Properties, then go to the Compatibilty tab. Select Force the use of a specific Steam Play compatibilty tool and then select Proton 11.
<br></br>
<br></br>

### <p align="center"> <img width="546" height="60" alt="configuring game settings" src="https://github.com/user-attachments/assets/1da44a96-a0d3-438d-8600-6f2568b5d6a6" /> </p>

- In the top-right corner of MO2, open the drop-down menu labeled Nuclear Sunset and select Configuring Game Settings, and click Run.
- Navigate to Options and select the Ultra preset. Ultra is the intended preset for Nuclear Sunset, however if you have a weaker computer, consider selecting the High or Medium presets. The presets will uniformly downsize all of the textures in Nuclear Sunset. Do not select the Low preset. This will disable critical rendering functions.
- Uncheck the Windowed option if the box is ticked.
- Click Ok and close the launcher.
<br></br>
<br></br>

### <p align="center"> <img width="546" height="60" alt="installing tale of two wasteland (TTW)" src="https://github.com/user-attachments/assets/a57f42cf-4879-4689-8fe0-468bee211c33" /> </p>

- Jackify has an in-built installer for Tale of Two Wastelands. Do not use the installer included with the download from modpub. Its dated and does not run nicely in Wine or Proton, and will take significantly longer than Jackify will. Jackify will also auto-detect file paths for Fallout 3 and Fallout: New Vegas for you and verify they are installed.
- Download the Tale of Two Wastelands file from modpub if you haven't already and extract the archive.
- In Jackify, go to the Tools Hub and find the TTW Linux Installer. Install it if it isn't already installed, then launch it.
- In TTW .mpi File location, select Browse and navigate to where you extracted the archive, and select the .mpi file.
- In Output Directory, select Browse and navigate to NuclearSunset/mods/ and select [NoDelete] [INF] [DB] - Tale of Two Wastelands (TTW) as the folder.
- Start the installation, and wait.
<br></br>
<br></br>

### <p align="center"> <img width="546" height="60" alt="running 4gb patcher" src="https://github.com/user-attachments/assets/fdcbb225-2f8f-4f3c-bf5c-25aef5371d86" /> </p>

- Download and extract the FNV 4GB for Linux archive if you haven't already to ~/NuclearSunset/[NoDelete]\ Stock\ New\ Vegas. 
- Right click on FalloutNVPatcher, go to Properties, and open the Permissions tab. 
- Under Execute:, tick the box that says Allow executing file as program, then hit OK. 
- Run FalloutNVPatcher.
    Terminal commands
    `cd ~/NuclearSunset/[NoDelete]\ Stock\ New\ Vegas/`
    `chmod +x FalloutNVPatcher && ./FalloutNVPatcher`
