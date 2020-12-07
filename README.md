# dwm - dynamic window manager | my custom build
[dwm](https://dwm.suckless.org/) is an extremely fast, small, and dynamic window manager for X.

dwm out of the box has the necessary features. Through patches you can determine what features you would like to add. patches can be found on the [suckless.org](https://dwm.suckless.org/patches/) website. The patches that I added:  
| | |
| :---: | :---: |
alpha | staticstatus
center | steam
cyclelayouts | swallow
focusonnetactive | [switchtag](https://github.com/bakkeby/patches/blob/master/dwm/dwm-switchtag-6.2.diff)
fullscreen | tagothermonitor
pertag | [tagswapmon](https://github.com/bakkeby/patches/blob/master/dwm/dwm-tagswapmon-6.2.diff)
scratchpads | vanitygaps
stacker | warp


## Features
+ Add indicator line on active or occupied tag which color can be changed in config.h
+ Pertag keeps settings per tag
+ Vanitygaps for gaps between windows and screen
+ Scratchpad for quick access to terminal
+ Swallow for saving space when a program is opend trough a termnial
+ Included layouts:
  + Bound to key: tile, monocle, spiral, bstack, floating (`MODKEY + t/m/y/u/f`)
  + Not bound to key: dwindle, deck, bstackhoriz, grid, nrowgrid, horizgrid, gapplessgrid, centerdmaster, centerdfloatingmaster


## Dependencies
In order to build dwm you need:
+ libxft (or [libxft-bgra](https://aur.archlinux.org/packages/libxft-bgra/) for colored font and emojis)
+ st
+ dmemu
+ ttf-joypixels

Optional programs
+ picom (transparency)
+ playerctl (audio ctl)
+ pamixer (volume ctl)
+ scrot (screenshot)


## Installation
Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):

    make clean install


## Running dwm
Add the following line to your .xinitrc to start dwm using startx:

    exec dwm


## Configuration
The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.  
Afterwards enter the following command to (re)build and install dwm (if
necessary as root):

    make install


## Custom keybindings
| Keybinding | Action |
| :--- | :--- |
|**General**|
| `MODKEY + j/k` | Move window up/down the stack |
| `MODKEY + shift + t` | Toggle picom |
| `MODKEY + ~` | Toggle terminal scratchpad |
| `MODKEY + shift + ~` | Toggle ranger (filemanger) scratchpad |
| `MODKEY + shift + f` | Toggle fullscreen layout |
| `MODKEY + ctrl + ,/.` | Switch next/previous layout |
| `MODKEY + SECMODKEY + (/shift+) u` | Increase/decrease gaps |
| `MODKEY + SECMODKEY + (/shift+) i` | Increase/decrease inner gaps |
| `MODKEY + SECMODKEY + (/shift+) o` | Increase/decrease outer gaps |
| `MODKEY + SECMODKEY + 0` | Toggle gaps |
| `MODKEY + SECMODKEY + shift + 0` | Reset default gaps |
| `MODKEY + shift + backspace` | Quit dwm |
|**Multi monitor** |
| `MODKEY + SECMODKEY + 1-9` | View tag on next monitor |
| `MODKEY + SECMODKEY + shift + 1-9` | Move window to tag next monitor |
| `MODKEY + SECMODKEY + ctrl + 1-9` | Move all windows to tag next monitor |
| `MODKEY + SECMODKEY + ctrl + ,/.` | Swap all windows on active tag between next/previous monitor |
