## Lolbox

My Livebox (Orange home gateway) has to be hard reboot several times a week to do its job.
This script provides an "cronable" way to do this from command line.

## Installation

As root :
```
cp livebox-reboot /usr/local/bin/
chmod +x /usr/local/bin/livebox-reboot
cp systemd/* /usr/lib/systemd/system/
```

Edit ```/usr/local/bin/livebox-reboot``` to set your livebox ip and credentials

Enable systemd timer :
```
systemctl daemon-reload
systemctl start livebox-reboot.timer
systemctl enable livebox-reboot.timer

systemctl list-timers
```

Systemd task will reboot your livebox every day at 5:30 AM.
