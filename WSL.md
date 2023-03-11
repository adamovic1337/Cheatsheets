# WSL Cheatsheet
For whole list of commands check [documentation](https://learn.microsoft.com/en-us/windows/wsl/basic-commands).
## Full list of commands:
```powershell
wsl --help
```
## Install
```powershell
wsl --install
```
Install WSL and default Ubuntu distribution.

- `--distribution`: Specify the Linux distribution to install. You can find available distributions by running `wsl --list --online`.
- `--no-launch`: Install the Linux distribution but do not launch it automatically.
- `--web-download`: Install from an online source rather than using the Microsoft Store.
- `--inbox`: Installs WSL using the Windows component instead of using the Microsoft Store. (WSL updates will be received via Windows updates, rather than pushed out as-available via the store).
- `--enable-wsl1`: Enables WSL 1 during the install of the Microsoft Store version of WSL by also enabling the "Windows Subsystem for Linux" optional component.
- `--no-distribution`: Do not install a distribution when installing WSL.
## List available Linux distributions
```powershell
wsl --list --online
```
## List installed Linux distributions
```powershell
wsl --list --verbose
```
## Set WSL version to 1 or 2
```powershell
wsl --set-version <distribution name> <versionNumber>
```
## Set default WSL version
```powershell
wsl --set-default-version <Version>
```
## Set default Linux distribution
```powershell
wsl --set-default <Distribution Name>
```
## Change directory to home
```powershell
wsl ~
```
## Run a specific Linux distribution from PowerShell
```powershell
wsl --distribution <Distribution Name> --user <User Name>
```
## Update WSL
```powershell
wsl --update
```
## Check WSL status
```powershell
wsl --status
```
## Run as a specific user
```powershell
wsl --user <Username>
```
## Check WSL version
```powershell
wsl --version
```
## Change the default user for a distribution
```powershell
<DistributionName> config --default-user <Username>
```
## Shutdown
```powershell
wsl --shutdown
```
## Terminate
```powershell
wsl --terminate <Distribution Name>
```
## Unregister or uninstall a Linux distribution
```powershell
wsl --unregister <DistributionName>
```