# mini-wpchanger

This is my mini wallpaper changer.

After using __variety__ wallpaper changer (http://peterlevi.com/variety/) for a couple of years (and downloaded hundreds of wallpapers), I decided to roll my own mini version with only the features I use and keeping the resource usage to a minimum.

![my desktop](https://github.com/gabdub/mini-wpchanger/blob/master/screencap/desktop1.jpg "my desktop")

__installation__
Just clone the repository somewhere, copy the files of your screen resolution, add some wallpapers to __wallpapers__ folder (adjust the files to your screen resolution) and run __choose_wp__ from cron every minute and at start up.

**Set your desktop**
Set your desktop's method of changing wallpaper in the last line of __stamp_date__. Use __~/.config/variety/scripts/set_wallpaper__ from __variety__ as a reference.
For Ubuntu Mate 16.04 use: __gsettings set org.mate.background ...__

**Add to cron**
```
crontab -e

* * * * * /bin/bash /home/.../choose_wp

^O enter (to save)
^X       (to exit)
```

**Add to start up**
Add a start up file to run:
```
/bin/bash /home/.../choose_wp
```
