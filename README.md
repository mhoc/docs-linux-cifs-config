## Problem 

Synology's CIFs/SMB server requires some level of non-default config, and every time it needs configuring it takes 
non-zero amount of time and retries to track down the proper configuration string for `/etc/fstab`.

## Solution

- On arch:

```
sudo pacman -S cifs-utils
```

- Append to `/etc/fstab`:

```
//192.168.1.100/share /home/mike/nas/share cifs username=USERNAME,password=PASSWORD,dir_mode=0777,file_mode=0777,vers=2.0 0 0
```

- Reload the changes in `/etc/fstab`

```
sudo systemctl daemon-reload
```

- Mount the share:

```
sudo mount -a
```

- When making changes, unmount the share, make the change, reload the change, mount.

```
sudo umount /home/mike/nas/share
```
