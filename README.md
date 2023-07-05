# V-Raptor SQ Nano : Personal Setup Note

```message
FIRST CREATE AT 2023-07-05
```

- All logs are just for memorize what was wrong and how to trouble-shoot

## RESET

- Based on official guide: [yona](https://yona.xslab.co.kr/%EC%97%91%EC%84%B8%EC%8A%A4%EB%9E%A9/HOWTO-V-Raptor-SQ-nano/post/23)

```shell
# To enter UEFI setup, press ESC when turn on
# But grub shell appears at first time.
grub> reboot

# After reboot, Can select boot options (in TeraTerm/minicom)
# 'Press ESCAPE for boot options ...' will appear and press ESC
```

## SSH

- At the first time, it is preferred to update APT packages.

```bash
# In my case, 97 packages upgraded
sudo apt-get update -y && sudo apt-get upgrade -y
```

## timezone setting

```shell
Current default time zone: 'Asia/Seoul'
Local time is now:      Wed Jul  5 23:10:51 KST 2023.
Universal Time is now:  Wed Jul  5 14:10:51 UTC 2023.
Run 'dpkg-reconfigure tzdata' if you wish to change it.
```

- If device is located outside of Korea(South)

```bash
### type below to set up timezone
## timezone for Ubuntu
# Solution 1) interactive mode
sudo dpkg-reconfigure tzdata
# Solution 2)
sudo timedatectl set-timezone America/Chicago 
## timezone for snap (optional)
sudo snap set system system.timezone="America/Chicago"
## check ubuntu timezone
timedatectl
```
