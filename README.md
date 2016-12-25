# mini-wpchanger

This is my mini wallpaper changer.

After using __variety__ wallpaper changer (http://peterlevi.com/variety/) for a couple of years (and downloaded hundreds of wallpapers), I decided to roll my own mini version with only the features I use while keeping the resource usage to a minimum.

![my desktop](https://github.com/gabdub/mini-wpchanger/blob/master/screencap/desktop1.jpg "my desktop")

__Installation:__

Just clone the repository somewhere, copy the files of your screen resolution, add some wallpapers to __wallpapers__ folder (adjust the files to your screen resolution) and run __choose_wp__ from cron every minute and at start up.

**Digital-7 font:**

Get and install __Digital-7-MonoItalic__ font from: http://www.dafont.com/es/digital-7.font

**Set up your desktop:**

Set up your desktop's method of changing the wallpaper in the last line of __stamp_date__ script.

Use __~/.config/variety/scripts/set_wallpaper__ from __variety__ as a reference.

For Ubuntu Mate 16.04 I use: __gsettings set org.mate.background ...__

**Add to cron**

```
crontab -e

* * * * * /bin/bash /home/.../choose_wp

^O enter (to save)
^X       (to exit)
```

**Run at startup**

Add this to run at startup:
```
/bin/bash /home/.../choose_wp
```

**Add caja-actions**

Caja actions packet allows you to configure Caja file manager context menus.

```
sudo apt install caja-actions
```

Add the following actions:

* __next wallpaper__ (folder action) - run: /install-path/next_wp - working folder: /install-path
* __play wallpaper list__ (folder action) - run: /install-path/start_playlist - working folder: /install-path
* __set this wallpaper__ (file action) - run: /install-path/showthis_wp - parameters: %F - working folder: /install-path

**changer mode**

Edit __mode__ file or run __start_playlist__ to change the wallpaper changer mode.

Allowed values:

* __0__ : keep the same wallpaper
* __1__ : random change the wallpaper every minute
* __2__ : random change the wallpaper every 5 minutes (since last change)
* __3__ : random change the wallpaper every 5 minutes (at minute 00, 05, 10, ..., 55)
* __4__ : play the wallpaper list (set a new wallpaper from the list every minute). the last line sets a new mode (set to 4 to repit the list for ever)
