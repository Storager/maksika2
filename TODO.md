1. Create user
2. Set tty

```
 #sudo  vi /etc/systemd/system/getty@tty1.service.d/override.conf
[Service]
ExecStart=
ExecStart=-/sbin/agetty -a <username> --noclear %I $TERM
```

3. install dependencies
```
sudo apt-get install --no-install-recommends xserver-xorg x11-xserver-utils xinit chromium-browser openbox -y
```

4. edit xorg autostart


```
# Disable any form of screen saver / screen blanking / power management
xset s off
xset s noblank
xset -dpms
# Allow quitting the X server with CTRL-ATL-Backspace
setxkbmap -option terminate:ctrl_alt_bksp
# Start Chromium in kiosk mode
sed -i 's/"exited_cleanly":false/"exited_cleanly":true/' ~/.config/chromium/'Local State'
sed -i 's/"exited_cleanly":false/"exited_cleanly":true/; s/"exit_type":"[^"]\+"/"exit_type":"Normal"/' ~/.config/chromium/Default/Preferences
chromium-browser --disable-infobars --kiosk '<http://your-url-here>'
```


5. Bash profiles
```
#nano .bash_profile
[[ -z $DISPLAY && $XDG_VTNR -eq 1 ]] && startx
```