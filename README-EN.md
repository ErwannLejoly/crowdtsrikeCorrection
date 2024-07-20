```markdown
# crowdtsrikeCorrection
# Instructions for Removing the File Affected by CrowdStrike in Safe Mode

## Objective
Remove the `C-00000291*.sys` file from the `C:\Windows\System32\drivers\crowdstrike` directory to fix the issue related to CrowdStrike.

## Steps to Follow

### 1. Restart Windows in Safe Mode
- **Restart your computer.**
- As the PC starts to boot, repeatedly press the `F8` key (or `Shift + F8` on some systems) until the Advanced Boot Options menu appears.
- In the menu, select `Safe Mode` or `Safe Mode with Networking` using the arrow keys and press `Enter`.

### 2. Open PowerShell as Administrator
- Press `Windows + X` to open the Power User menu.
- Select `Windows PowerShell (Admin)`.

### 3. Prepare the PowerShell Script
- Create a new text file and copy the following script into it.
- Save the file with a `.ps1` extension, for example, `Remove-CrowdStrikeFiles.ps1`.
- Alternatively, you can clone the script.

### 4. Run the Script
- Navigate to the directory where you saved the script.
- Run the script by entering the following command in PowerShell:

```powershell
cd C:\path\to\script
.\Remove-CrowdStrikeFiles.ps1   
```

### 5. Verify the Removal
- After running the script, check the `C:\Windows\System32\drivers\crowdstrike` directory to ensure that all files matching the pattern `C-00000291*.sys` have been deleted.

### 6. Restart in Normal Mode
- Restart your computer normally.

## Additional Notes
- **Administrative Rights**: Ensure you have administrative privileges to delete system files.
- **Backup**: It is advisable to back up critical data before modifying system files.
- **Testing**: Test the script in a controlled environment before deploying it on production systems.

By following these steps, you can effectively remove the specified files from your system to fix the issue related to CrowdStrike.
```

