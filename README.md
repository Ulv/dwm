my dwm (tiling window manager) with patches
-------------------------------------------

dwm - suckless.org

+ attachaside patch
+ pango patch
+ systray patch

* Fixed bottom+right gaps in xterm
* Modifier set to win key

dwm misc. options (for ubuntu 14)

To show wlan ssid, laptop battery percentage, clock and language in dwm bar pu this code in /etc/X11/Xsession.d/89-custom-options

    # dwm title
    while true; do
        wlan=$(iwgetid | awk '{$1=""; print substr($0,8)}')
        batt=$(upower -i /org/freedesktop/UPower/devices/battery_BAT1 | grep -E "percentage" | xargs | sed -e 's/percentage/Bat/g')
        xsetroot -name "$(xkb-switch) / WiFi: $wlan / $batt / $(date +'%F %R')"
        sleep 1m
    done &

To fix java apps render (install wmname first)

    # Fix java apps
    wmname LG3D

setxkbmap options with menu toggle and replace caps lock key with ctrl

    # caps = ctrl
    setxkbmap -option ctrl:nocaps
    setxkbmap -layout us,ru -option grp:menu_toggle

Vladimir Chmil <vladimir.chmil@gmail.com>

