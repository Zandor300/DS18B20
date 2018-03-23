# DS18B20
Simple PHP Code to automatically read and display DS18B20 names and temps to a php page on a Raspberry Pi.

## Instructions
You will need to setup the pi to add OneWire support
Start by adding the following line to /boot/config.txt
You can edit that file with nano by running `sudo nano /boot/config.txt` and then scroll to the bottom and type

```
dtoverlay=w1-gpio
```

Press Ctrl + X and Y to confirm, then run `sudo nano /etc/modules`.

Add the following 2 lines to the bottom:
```
w1-gpio
w1-therm
```

Press Ctrl + X and Y to confirm, then reboot your Pi.

Add temp.php to /var/www/html then visit http://127.0.0.1/temp.php or http://[IP OF PI]/temp.php

Page output should look similar to this:
```
Sensor ID#: 28-0214640d18ff = 26 °C / 79 °F 
Sensor ID#: 28-02146409b9ff = 25 °C / 77 °F
```
