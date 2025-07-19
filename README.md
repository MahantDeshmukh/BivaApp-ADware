# BivaApp Adware Removal Guide

**BivaApp** is a potentially unwanted application that:
- Installs via deceptive pop-up ads or free software bundles
- Hijacks browser settings
- Injects unwanted ads/popups
- Collects browsing and login data
- Reinforces its presence through startup tasks, scheduled tasks, or the registry

> **Symptoms:**  
> - Suspicious startup/background activity  
> - BivaApp listed in "Apps & Features" or Control Panel but *can't be uninstalled* (error: file not found)  
> - Reappears after manual deletion due to persistent components

---

## Incident Summary

During system cleanup, BivaApp was discovered to have been stealthily installed with third-party software. Uninstall attempts failed due to broken uninstallers, and removal was undone at every restart. Analysis found the cause to be registry and scheduled task persistence.

---

## Step-by-Step Removal Instructions

1. **Kill Running Processes**
   - Open **Task Manager**
   - Look for `BivaApp`, `Bivaji`, or unknown/suspicious tasks
   - Right-click → **End Task**

2. **Delete Files Manually**
   - Go to:  
     `C:\Users\<YourName>\AppData\Roaming\BivaApp`  
     Delete the `BivaApp` folder
   - Also check these directories and delete any `BivaApp` entries:  
     - `%APPDATA%`
     - `%LOCALAPPDATA%`
     - `C:\ProgramData`

3. **Remove from Startup**
   - Press `Win + R` → type: `shell:startup`
   - Delete any `BivaApp.lnk` or suspicious shortcuts
   - In Task Manager, **Startup** tab: disable anything suspicious

4. **Delete Scheduled Tasks**
   - Press `Win + R` → type: `taskschd.msc`
   - Open **Task Scheduler Library**
   - Delete tasks named `BivaApp`, `Update`, `Startup`, or random strings

5. **Clean the Registry**
   > **Warning:** Editing the registry can harm your PC. Proceed with caution!
   - Press `Win + R` → type: `regedit`
   - Navigate to:  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall`
   - Look for folders/keys with `DisplayName = BivaApp` (or "bivaapp"), right-click, and **Delete**
   - Also check:  
     `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Uninstall`

6. **Scan Your System for Malware**
   - Open **Microsoft Defender**  
     `Virus & threat protection` → **Full Scan**
   - Optionally run **Defender Offline Scan** for deep/rootkit threats

7. **Reset Browsers (If Hijacked)**
   - **Chrome:**  
     Go to `chrome://settings/reset` → Click **Restore settings to original defaults**
   - **Edge:**  
     Go to `edge://settings/reset` → **Reset settings**
   - **Firefox:**  
     Go to `about:support` → Click **Refresh Firefox**

8. **Change Passwords & Enable 2FA**
   - Change passwords for all critical accounts (Gmail, Steam, Instagram, Riot, etc.)
   - Enable **Two-Factor Authentication (2FA)** wherever supported

---

## Additional Notes

- This guide is current and effective as of **July 2025**
- BivaApp often comes bundled with pirated or "free" software—avoid downloading cracked tools or games
- Always use *custom install* mode and *deselect third-party offers* during software installation

---

**Author:** Mahant Deshmukh  
**Date:** 10-07-2025  
**Version:** 1.0
