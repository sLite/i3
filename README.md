# i3 - improved tiling wm

The most awesome window manager known to mankind. Period.
Homepage: http://i3wm.org

## Purpose of this repo

Vanilla i3 doesn't play that well with KDE/Plasma, and i love KDE, that's why i'm maintaining this repo.

Up until now i just added code and haven't modified vanilla i3 code. I will try to stick to this in the future ensuring simple merges.

### Branches

* **master, next**: those will stay vanilla for easy fast-forward merges of the official i3 repo

* **kde-master**: that's what you want if you want to use i3 with KDE/Plasma

I won't maintain an up-to-date **next** branch with KDE/Plasma patches included, if you need that, feel free to clone :)

### Features

* Proper handling of KDE/Plasma popups and floating panels (mostly widget stuff) (_NET_WM_STATE_STAYS_ON_TOP)

### i3-config

The following settings are recommended:

```
# general application settings
for_window [window_role="pop-up"] floating enable
for_window [class="plasmashell"] floating enable

# close plasma desktop windows
for_window [title="Desktop — Plasma"] kill;

# disable focus
no_focus [class="plasmashell"]
no_focus [window_role="pop-up"]
no_focus [window_type="notification"]

focus_on_window_activation none
focus_follows_mouse no
mouse_warping none
```

If you are running a multi monitor setup, depending on the monitor setup, you might run into problems with krunner and systray popups not opening properly. Opening on the wrong screen or just flickering and staying invisible.

This might be related to the following KDE bug (https://bugs.kde.org/show_bug.cgi?id=344328). 
I found this workaround for krunner there and also applied it to the plasmashell.

```
# restart krunner & panel because of broken multimonitor handling
exec --no-startup-id sleep 5 && kquitapp5 plasmashell && kstart plasmashell
exec --no-startup-id sleep 5 && kquitapp5 krunner && kstart krunner
```

If you want kmix, kcalc and those other small tools floating, those are settings you still have to do with your i3 config.

### Credits

* Michael Stapelberg for this awesome project, and all the contributors for their work.
* Marius Muja for his KDE fixes on earlier versions of i3. They were a gamechanger, and without them i probably would have swiched back to KWM and would be unhappy for the rest of my life ;) I owe you some beers! I basically just ported his patches to 4.8 and left out what isn't necessary anymore.
