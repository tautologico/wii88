# About wii88

This project is a fork from [QUASI88](https://www.eonet.ne.jp/~showtime/quasi88/) version 0.6.4, a NEC PC-8801 emulator by Showzoh Fukunaga.
Specifically, the source [quasi88-0.6.4.tgz](https://www.eonet.ne.jp/~showtime/quasi88/release/quasi88-0.6.4.tgz) (md5sum '21d268aaa290471f60142fea49485010').
The main purpose of this fork is to be used with Nintendo Wii.
We also used for reference the [QUASI88 Wii port](http://wiibrew.org/wiki/QUASI88) version 0.6.3 beta6 by [Rako](http://wiibrew.org/wiki/User:Rako).

## Download

For public releases, please check the [releases](https://github.com/jpzm/wii88/releases) page. For the latest development version, you may clone the `master` branch with the below command.
```
$ git clone https://github.com/jpzm/wii88.git
```
The content of the repository folder `hbc` has the files of the latest compiled version.

## Setup

In order to setup the port, you have to:
  + copy the content of the download release (or the `hbc` repository folder) to your SD/SDHC card.
  + copy system roms files to sd:/wii88/rom directory.
  + copy game roms files to sd:/wii88/disk directory.

The emulation performace is better with original NEC PC8801 roms, but you can also use the pseudo BIOS available [here](http://www.retropc.net/cisc/m88/download.html).

## Usage

When pointed to the screen, it is possible to use the Wii Remote to control the emulator options.
You can use the Wii Remote as a mouse cursor.
To open the menu, press the Wii Remote plus button (mapped to F12 key).
The Wii Remote minus button could be used to exit the menu (mapped to ESC key).
To select a game image, go to the DISK tab, select the game disk file (.d88), and push the OK.
Finally, go to the RESET tab, select the according BASIC MODE for your game, and push the RESET button.

On release 0.1.1, it is possible to change button mappings and/or create independent mappings for each game image.
See [`hbc/wii88/rc/default.rc`](https://github.com/jpzm/wii88/blob/master/hbc/wii88/rc/default.rc) and [`src/keyboard.h`](https://github.com/jpzm/wii88/blob/master/src/keyboard.h#L172) for guidance.
For example, if there is a image file named `Game.d88` in `disk` directory and a mapping file named `Game.d88.rc` in the `rc` directory, the custom key mappings are loaded from `Game.d88.rc`.
Otherwise, the mapping from `default.rc` file is used.

## Build

To build the Wii port, please use the provided `Makefile.wii`.
In the terminal, you may type `make -f Makefile.wii`.
If everything proceed sucessfully, there will be a new `wii.dol` file.
This file is also copied to `hbc/apps/wii88/boot.dol`.

### Required libraries

* SDL-wii

To compile SDL-wii you'll need:
* libogg
* libvorbisidec
* libjpeg
* libpng
* freetype

## Credits

In this Wii port I tried to modify the original code from QUASI88 as less as possible. The additional code and build files are almost always apart the original files. Therefore, the emulation process itself is cretited to Showzoh Fukunaga (the original QUASI88 author). Also, the included `icon.png` file was created by [NeoRame](http://neorame.de/pre/).
