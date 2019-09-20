# Sauron - the all seeing eye

The all-seeing keylogger. Logs on pre-defined device.

## Ignite fires of mount doom
This will enable us to bring sauron to life:  

`Install https://github.com/kernc/logkeys`

## Create Sauron
Create a bash script, `sauron.sh`:  
```
#!/bin/bash
sudo  logkeys -s --keymap /path_to_keymap/en_US_ubuntu_1204.map -d event9 --output /output_path/sauron_knowledge
```

### Configure sauron

`--keymap` uses keymap. For ubuntu, use the above keymap.

`-d` option to map device. Identify external device by:  
`cat /dev/input/eventX`

## Awaken Sauron on bootup

Set a crontab for this at `sudo vim /etc/crontab` and add at end:
```
@reboot root sh /path_to_sauron/sauron.sh
```

## Destroy Sauron's knowledge

Run `narsil.sh`:

```
#!/bin/bash
sudo bash -c "> /output_path/sauron_knowledge"
```

## Notify that sauron is watching

Create the shell file that displays warning, `notify_sauron_is_watching.sh`: 
```
#!/bin/bash
notify-send "sauron is watching"
```

Create `sauron_reminder.desktop` in `/etc/xdg/autostart` with the contents:

```
[Desktop Entry]
Exec=/path_to_warning/notify_sauron_is_watching.sh
Name=Notify keylogger is on
Encoding=UTF-8
Terminal=true
Type=Application
Categories=Application;
X-GNOME-Autostart-Delay=5
```

enable executing permission:
`chmod +x ./warning.desktop`

## Manually manage Sauron

Kill logkeys:
```
sudo logkeys -k
```

Start logkeys:  
```
sudo  logkeys -s --keymap en_US_ubuntu_1204.map  -d event9 --output ~/oracle
```
