# docs-linux-cifs-config

This is just for my own personal use.

## Problem 

Synology's CIFs/SMB server requires some kind of non-default config, and every time it needs configuring it takes 
non-zero amount of time and retries to track down the proper configuration string for /etc/fstab.

## Solution

Append to `/etc/fstab`:

```
//192.168.1.100/share /home/mike/nas/share cifs username=USERNAME,password=PASSWORD,dir_mode=0777,file_mode=0777,vers=2.0 0 0
```
