# Autorun_logkeys

## Autorun

Create a bash script:
```
#!/bin/bash
sudo  logkeys -s --keymap /home/varun/code/z_archive/autorun/en_US_ubuntu_1204.map  -d event9 --output /home/varun/oracle

```

Set a crontab for this at `sudo vim /etc/crontab` and add at end:
```
@reboot root sh /home/varun/code/z_archive/autorun/startup.sh
```

## Start / stop

Kill logkeys:
```
sudo logkeys -k
```

Start logkeys:  
```
sudo  logkeys -s --keymap en_US_ubuntu_1204.map  -d event9 --output ~/oracle
```

`--keymap` uses keymap. For ubuntu, use the above keymap.

`-d` option to map device. Map external keyboard. Identify by: `cat /dev/input/eventX`

