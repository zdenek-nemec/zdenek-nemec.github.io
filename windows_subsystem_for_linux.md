# Windows Subsystem for Linux

## Installation

Sources

* [Microsoft guide](https://docs.microsoft.com/en-gb/windows/wsl/install-manual)

### Instructions

1. Enable Virtual Machine Platform and Windows Subsystem for Linux

    * Run PowerShell as administrator and execute following:

        ```powershell
        dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
        dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
        ```

    * Or go to Settings > Apps > Programs and Features > Turn Windows features on or off and tick following:

        * Virtual Machine Platform
        * Windows Subsystem for Linux

2. Restart

3. Install Ubuntu (e.g. 20.04)

    * From Microsoft Store

    * Or manually

        1. From [WSL Ubuntu Package](https://aka.ms/wslubuntu2004) download `*.appx` file
        2. Install by opening the downloaded file in File Exlorer
        3. During the installation setup username and password for the Linux subsystem

4. Download and run [WSL2 Linux kernel update package for x64 machines](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)

5. Run PowerShell as administrator and check that Ubuntu subsystem is installed

    ```powershell
    wsl --list --verbose
    ```

6. Setup WSL version 2

    ```powershell
    wsl --set-default-version 2
    wsl --set-version DISTRIBUTION_NAME 2
    ```

---

## Keeping Linux Up-to-Date

After the installation is finished and later from time to time you should update the Linux system. To do this just execute the following commands.

```bash
sudo apt-get update
sudo apt-get upgrade
```
