# GPOS
A set of LGPO exported GPOs that can be imported to alternate between benchmarking and daily use modes.

## Setup

Download LGPO from Microsoft (it's part of the Microsoft Security Compliance Toolkit 1.0) and add ```LGPO.exe``` to your PATH.

https://www.microsoft.com/en-us/download/details.aspx?id=55319

## Current GPO Sets

### bench

Provides settings for accurate benchmarking. At the moment, they

- Disable Windows Defender
- Disable Windows Update
- Disable Windows Store updates
- Disable Cortana
- Disable OneDrive
- Disable Windows Firewall

OBS.: Be sure to manually disable Tamper Protection in Windows Defender before applying the settings, otherwise everything related to Windows Defender will be reset shortly after.

### daily

They re-enable everything that is disabled by 'bench' and

- Defer Windows Updates by 7 days
- Defer major Windows build updates by 30 days

## Export Local Group Policy Settings

To create a backup for local policy settings on your local PC, run this command at Command Prompt:

```LGPO.exe /b backup_path```

## Import Local Group Policy Settings

To restore Local Group Policy settings from the backup, import them by running the following command:

```LGPO.exe /g backup_path```
