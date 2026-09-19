There are two ways to set charge thresholds
1. In BIOS there will be a setting to put charge start and charge end battery percentages (ex: 50-60)
	1. In power settings
2. edit /sys/class/power_supply/BAT0/charge_control_start_threshold and /sys/class/power_supply/BAT0/charge_control_end_threshold

when editing BAT0 files, it is important to set up a cron job to set the thresholds again on reboot or else they will be restored to defaults 

ex crontab:
```
@reboot echo 50 | sudo tee /sys/class/power_supply/BAT0/charge_control_start_threshold
/sys/class/power_supply/BAT0/charge_control_end_threshold
```
