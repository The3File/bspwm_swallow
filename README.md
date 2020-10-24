# swallow

> rewrite of [bspswallow](https://github.com/JopStro/bspswallow)

## configuration

### swallowing applications
by default `swallow` uses `xdg-mime` to get the default programs
for images, videos and pdfs with `images/*`, `videos/*` and
`application/pdf`.

you can specify your own by setting `$SWALLOW_APPLICATIONS` to
the class of the programs that you want to be swallowed in
ex. `profile` or `bashrc` (*lowercase*).

``` bash
# ~/.bash_profile
export SWALLOW_APPLICATIONS="sxiv zathura mpv"
```

> you can get the class of a program with `xprop | grep WM_CLASS`.

### terminals to swallow
the script contains an internal list for `st`, `urxvt` and `kitty`
but you can specify your own terminal(*s*) with (*lowercase*)

``` bash
# ~/.bash_profile
export SWALLOW_TERMINALS="xterm"
```

## usage
execute the script from ex. `.xinitrc` (*before bspwm*)
``` bash
# ~/.xinitrc
...
exec swallow &
bspwm &
```

## installation
`make` installs to `/usr/local` by default.
Install with `make PREFIX=/some/other/path` to change this. 

``` bash
git clone https://github.com/The3File/bspwm_swallow.git
cd bspwm_swallow
sudo make install
```

## dependencies
* `bspwm`
* `xprop`
* `xdg-utils` (*not needed if `$SWALLOW_APPLICATIONS` is set*)
