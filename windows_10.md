# Windows 10

## How To

### Black Accent Colour

1. Open Registry Editor
2. Navigate to `Computer\HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\DWM` directory
3. Set value of `AccentColor` to `ff000000`
4. Set value of `AccentColorInactive` to `ff000000`

### Home Directory

In case you need to change the home directory and cannot do it the standard way
use Registry Editor.

1. Open Registry Editor
2. Navigate to `Computer\HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Shell Folders`
3. Change the value of `Personal` to new path
4. Navigate to `Computer\HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders`
5. Change the value of `Personal` to new path
6. Identify hexadecimal key that matches the old path and change its value to new path
