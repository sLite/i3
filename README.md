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

* Proper handling of KDE/Plasma desktop (_NET_WM_WINDOW_TYPE_DESKTOP)
* Proper handling of KDE/Plasma popups and floating panels (mostly widget stuff) (_NET_WM_STATE_STAYS_ON_TOP)

### i3-config

No special settings needed.

If you want kmix, kcalc and those other small tools floating, those are settings you still have to do with your i3 config.

### Credits

* Michael Stapelberg for this awesome project, and all the contributors for their work.
* Marius Muja for his KDE fixes on earlier versions of i3. They were a gamechanger, and without them i probably would have swiched back to KWM and would be unhappy for the rest of my life ;) I owe you some beers! I basically just ported his patches to 4.8 and left out what isn't necessary anymore.
