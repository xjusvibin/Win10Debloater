# Windows 10 Debloat Utility
#
# Utility to remove pre-installed Windows 10 applications, disable telemetry functions, stop Cortana from being used as the search index, disable scheduled tasks, and perform additional system optimizations.
#
# Disclaimer
#
# Use this utility at your own risk. No responsibility is taken for any system issues that may arise. This utility is not affiliated with other similar projects, and comparisons to "new" versions may not be accurate.
#
# How To Run the Script Files
#
# Two script files are provided: one with a graphical user interface (GUI) and one without. Below are the methods to run them.
#
# Method 1: Manual Execution
#
# 1. Download the .zip file and extract it to a desired location.
# 2. Open PowerShell or PowerShell ISE as an Administrator.
# 3. Enable PowerShell script execution with the command:  
#    Set-ExecutionPolicy Unrestricted -Force
# 4. Change to the directory where the files were extracted, e.g., `cd c:\temp`.
# 5. Run the desired script, e.g., `.\Windows10DebloaterGUI.ps1`.
#
# Method 2: Quick Execution
#
# 1. Download the .zip file and extract it to a desired location.
# 2. Right-click the desired PowerShell script file and select "Run With PowerShell".
# 3. Confirm the prompt to allow the script to run.
#
# Note: Administrative privileges are required for proper functionality.
#
# How To Run the Silent Version
#
# The silent script (`Windows10SysPrepDebloater.ps1`) supports parameters: `-SysPrep`, `-Debloat`, and `-Privacy`. To run it with parameters:
#
# 1. Download the .zip file and extract it to a desired location.
# 2. Open PowerShell or PowerShell ISE as an Administrator.
# 3. Change to the directory where the files were extracted, e.g., `cd c:\temp`.
# 4. Run the script with parameters, e.g., `.\Windows10SysPrepDebloater.ps1 -SysPrep -Debloat -Privacy`.
#
# Script Variants
#
# Three versions are available:
#
# - Silent Version (`Windows10SysPrepDebloater.ps1`): Runs without user interaction using parameters `-SysPrep`, `-Debloat`, and `-Privacy`. Suitable for automated deployments, such as MDT imaging or sysprepping.
# - Interactive Version (`Windows10Debloater.ps1`): Prompts the user for choices during execution. Not intended for silent deployments.
# - GUI Version (`Windows10DebloaterGUI.ps1`): Provides a graphical interface with buttons for all functions. Designed for users preferring a visual interface over command-line interaction.
#
# Parameters for Silent Version
#
# The silent script supports the following parameters:
#
# - `-SysPrep`: Executes commands to prepare the system for app removal, using `Get-AppxPackage | Remove-AppxPackage`.
# - `-Debloat`: Removes specified applications, deletes associated registry keys, and applies privacy settings.
# - `-Privacy`: Modifies registry settings to disable telemetry, Cortana search integration, and unnecessary scheduled tasks.
#
# For optimal results, run the script before configuring a user profile to prevent leftover apps or broken Start menu tiles.
#
# Source Code
#
# This repository contains PowerShell scripts for debloating and optimizing Windows 10. The scripts are organized into main executable files and a subfolder with modular components.
#
# Main Scripts
# - `Windows10Debloater.ps1`: Interactive script with command-line prompts to remove bloatware, disable telemetry, and adjust system settings. Suitable for manual execution with user input.
# - `Windows10DebloaterGUI.ps1`: Graphical user interface version with buttons for debloating, privacy settings, and reverting changes. Designed for users preferring a visual interface.
# - `Windows10SysPrepDebloater.ps1`: Silent script with optional parameters (`-SysPrep`, `-Debloat`, `-Privacy`) for automated debloating during system deployment or sysprep processes.
#
# Component Scripts
# The `ComponentScripts` subfolder contains individual PowerShell scripts that perform specific tasks. These are used by the main scripts or can be run independently:
# - `Clear Last Used Files and Folders.ps1`: Clears recent files and folders from Explorer history.
# - `Debloat Windows`: Removes pre-installed Windows 10 applications based on a predefined list.
# - `Disable Cortana`: Disables Cortana and its search integration.
# - `Disable Last Used Files and Folders View.ps1`: Hides recent files and folders in Explorer.
# - `Enable Cortana`: Re-enables Cortana functionality.
# - `Enable Edge PDF`: Restores Edge as the default PDF viewer.
# - `Fix Whitelisted Apps`: Reinstalls whitelisted apps if removed unintentionally.
# - `Protect Privacy`: Modifies registry settings to reduce telemetry and enhance privacy.
# - `Remove Bloatware RegKeys`: Deletes registry keys associated with removed bloatware.
# - `Revert Changes`: Restores removed apps and default settings.
# - `Set Explorers LaunchTo Computer.ps1`: Configures Explorer to open to "This PC" by default.
# - `Stop Edge PDF`: Prevents Edge from being the default PDF viewer.
# - `Uninstall OneDrive`: Removes OneDrive and its components.
# - `Unpin Start`: Unpins all tiles from the Start menu.
#
# Usage Notes
# - Main scripts require administrative privileges to function correctly.
# - Component scripts can be imported into custom workflows or run standalone with appropriate permissions.
# - File paths and script interactions assume execution from the repository root unless specified otherwise.
#
# Registry Keys Removed
#
# The following registry keys associated with removed applications are deleted:
#
# - EclipseManager
# - ActiproSoftwareLLC
# - Microsoft.PPIProjection
# - Microsoft.XboxGameCallableUI
#
# Functions Executed
#
# Debloat Option
# - Removes specified applications.
# - Deletes leftover registry keys.
# - Applies privacy settings.
# - Optionally stops Edge from being the default PDF viewer.
#
# Revert Option
# - Reinstalls removed applications.
# - Restores registry keys to default settings.
# - Optionally re-enables Edge as the default PDF viewer.
#
# Disabled Scheduled Tasks
#
# The following scheduled tasks are disabled with no impact on core OS functionality:
#
# - XblGameSaveTaskLogon
# - XblGameSaveTask
# - Consolidator
# - UsbCeip
# - DmClient
#
# Applications Removed
#
# The utility removes the following pre-installed Windows 10 applications:
#
# - 3DBuilder
# - Alarms
# - Appconnector
# - Asphalt8
# - Windows Camera
# - CandyCrush
# - CandyCrushSoda
# - Caesars Slots Free Casino
# - ContactSupport
# - Duolingo
# - EclipseManager
# - Facebook
# - FarmVille 2 Country Escape
# - Flipboard
# - Fresh Paint
# - Get Started
# - iHeartRadio
# - Maps
# - March of Empires
# - Messaging
# - Microsoft Office Hub
# - Microsoft Solitaire Collection
# - Microsoft Sticky Notes
# - Minecraft
# - Netflix
# - Network Speed Test
# - NYT Crossword
# - Office Sway
# - OneNote
# - OneConnect
# - Pandora
# - People
# - Phone
# - Phototastic Collage
# - PicsArt-PhotoStudio
# - PowerBI
# - Royal Revolt 2
# - Shazam
# - Skype for Desktop
# - SoundRecorder
# - TuneInRadio
# - Twitter
# - Windows Communications Apps
# - Windows Feedback
# - Windows Feedback Hub
# - Windows Reading List
# - XboxApp
# - Xbox Game CallableUI
# - Xbox Identity Provider
# - Zune Music
# - Zune Video
#
# Allowlist and Blocklist
#
# In the GUI version, applications marked in the blocklist are targeted for removal.