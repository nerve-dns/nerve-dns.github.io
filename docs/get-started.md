---
sidebar_position: 1
---

# Getting started

> **_NOTE:_**  Be cautious when directly executing scripts from an URL. You can watch the content of the script [here](https://raw.githubusercontent.com/nerve-dns/nerve/0d84cbbf5a5a3e496ffc5f7d2db727ef8f4e1af2/scripts/install.ps1) before continuing.

## Windows

The script will just download the latest release, unpack it to LOCALAPPDATA\Programs\Nerve and optionally install Nerve as a service.

Execute the following in a administrator powershell console (go to start, search for "powershell", right click and click "run as administrator"):
```powershell
iex ((New-Object System.Net.WebClient).DownloadString('https://raw.githubusercontent.com/nerve-dns/nerve/0d84cbbf5a5a3e496ffc5f7d2db727ef8f4e1af2/scripts/install.ps1'))
```