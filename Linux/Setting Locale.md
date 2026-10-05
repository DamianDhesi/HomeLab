for debian based distros, locale is in /etc/locale.conf and /etc/default/locale

if programs (like ansible) can't detect the locale, it may need to be edited (/etc/locale.conf) like so (for US english)
```
LANG=en_US.UTF-8
LANGUAGE=en_US
LC_ALL=en_US.UTF-8
```

can update locale without rebooting by doing
```
source /etc/default/locale
export LANG
```

to generate new language definitions that will apply after reboot use
```
sudo locale-gen
```