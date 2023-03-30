# Wallpaper Setup
A collection of tools to sort wallpapers by color, and apply theming.

## Deps
* [Perl](https://www.perl.org/)
* [Feh](https://feh.finalrewind.org/)
* [ImageMagick](https://imagemagick.org/index.php)
* [Make](https://www.gnu.org/software/make/)

## Extras
* [Pywal](https://github.com/dylanaraps/pywal)
* [Pywalfox](https://github.com/Frewacom/pywalfox)

## Install
Install dependencies on your system.

Download all files.

At the top of `walls` and `wall-log`, edit 
```
chdir '/home/c/img/bg'
```
to reflect your wallpaper directory.

Place `walls` and `wall-log` in your `$PATH`.

Place `themes` in `~/.config/feh/themes`.

Place `Makefile` in your wallpaper directory.

Run `make` from inside your wallpaper directory.
This will take a while, depending on how many wallpapers you have.

## Usage
Run `walls` to browse sorted wallpapers by hue.
It may take a while to generate all thumbnails the first time.
Click on a thumbnail to set as wallpaper.

If you get a new wallpaper, run `make` inside your wallpaper 
directory to add it to the color cache.

## Process
* ImageMagick crunches the image down to 1x1 and returns the color of the pixel
* The Hue and Lum are calculated from the color
* Images and colors are cached in `hues` in the same directory as `Makefile`.
* Feh displays images sorted by hue (or luminance if you change `$prop` in `walls`).
