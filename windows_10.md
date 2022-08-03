# Windows 10

## How To

### Black Accent Colour

1. Open Registry Editor
2. Navigate to `Computer\HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\DWM` directory
3. Set value of `AccentColor` to `ff000000`
4. Set value of `AccentColorInactive` to `ff3f3f3f`

### Home Directory

In case you need to change the home directory and cannot do it the standard way
use Registry Editor.

1. Open Registry Editor
2. Navigate to `Computer\HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer`
3. In `Shell Folders` change the value of `Personal` to the new path
4. In `User Shell Folders` change the value of `Personal` to the new path
5. In `User Shell Folders` identify the hexadecimal key that matches the old path and change its value to the new path

### Transparency

In case that the transparency/opacity effects do not work properly, check if
`Settings > Personalization > Colors > Transparency effects` is set to `On`
