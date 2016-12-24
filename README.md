# mini-wpchanger

This is my mini wallpaper changer.

After using __variety__ wallpaper changer for a couple of years (and downloaded hundreds of wallpapers), I decided to roll my own mini version with only the features I use and keeping the resource usage to a minimum.

![my desktop](https://github.com/gabdub/mini-wpchanger/blob/master/screencapt/desktop1.jmp "my desktop")

__installation__
Just clone the repository somewhere, copy the files of your screen resolution, add some wallpapers to __wallpapers__ folder (adjust the files to your screen resolution) and run __choose_wp__ from cron every minute and at start up.

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
