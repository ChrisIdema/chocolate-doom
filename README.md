# Chocolate Doom

Chocolate Doom aims to accurately reproduce the original DOS version of
Doom and other games based on the Doom engine in a form that can be
run on modern computers.

Originally, Chocolate Doom was only a Doom source port. The project
now includes ports of Heretic and Hexen, and Strife.

Chocolate Doom’s aims are:

 * To always be 100% Free and Open Source software.
 * Portability to as many different operating systems as possible.
 * Accurate reproduction of the original DOS versions of the games,
   including bugs.
 * Compatibility with the DOS demo, configuration and savegame files.
 * To provide an accurate retro “feel” (display and input should
   behave the same).

More information about the philosophy and design behind Chocolate Doom
can be found in the PHILOSOPHY file distributed with the source code.

## Build
https://www.chocolate-doom.org/wiki/index.php/Building_Chocolate_Doom_on_Windows

Follow these steps to build Doom on windows 10:

* install MSYS2 (tested with msys2-x86_64-20210725)
* `pacman -Syu`
* `pacman -Su`
* Run:
```
pacman -S base-devel msys2-devel \
mingw-w64-i686-{toolchain,SDL2{,_net,_mixer},libsamplerate,libpng} \
python zip git
```
* open MSYS2 MinGW 32-bit (via start menu or `C:\msys64\msys2_shell.cmd -mingw32`)
* `cd <path to repo>`
* `./autogen.sh --host=i686-w64-mingw32`
* `make`
* `cd pkg/win32`
* `make`
* `cd staging-doom`

## Run
Follow these steps to run Doom on windows 10:
* Get a wad file such as `doom1.wad` (free Shareware demo of Doom*) or `doom.wad` (Ultimate Doom, paid license**)
* `cd \pkg\win32\staging-doom`
* setup your keys by running `chocolate-doom-setup.exe` or remember path of cfg files
* `.\chocolate-doom.exe -iwad "<path to .wad file>"`
* or `.\chocolate-doom.exe -iwad "<path to .wad file>" -config "<path to default.cfg>" -extraconfig "<path to chocolate-doom.cfg>"`

\* you can get the free Shareware demo here https://www.doomworld.com/idgames/idstuff/doom/win95/doom95

\** you can buy Ultimate Doom at GOG https://www.gog.com/game/the_ultimate_doom for $2.50 at the time of writing

## Setting up gameplay

For instructions on how to set up Chocolate Doom for play, see the
INSTALL file.

## Configuration File

Chocolate Doom is compatible with the DOS Doom configuration file
(normally named `default.cfg`). Existing configuration files for DOS
Doom should therefore simply work out of the box. However, Chocolate
Doom also provides some extra settings. These are stored in a
separate file named `chocolate-doom.cfg`.

The configuration can be edited using the chocolate-setup tool.

## Command line options

Chocolate Doom supports a number of command line parameters, including
some extras that were not originally suported by the DOS versions. For
binary distributions, see the CMDLINE file included with your
download; more information is also available on the Chocolate Doom
website.

## Playing TCs

With Vanilla Doom there is no way to include sprites in PWAD files.
Chocolate Doom’s ‘-file’ command line option behaves exactly the same
as Vanilla Doom, and trying to play TCs by adding the WAD files using
‘-file’ will not work.

Many Total Conversions (TCs) are distributed as a PWAD file which must
be merged into the main IWAD. Typically a copy of DEUSF.EXE is
included which performs this merge. Chocolate Doom includes a new
option, ‘-merge’, which will simulate this merge. Essentially, the
WAD directory is merged in memory, removing the need to modify the
IWAD on disk.

To play TCs using Chocolate Doom, run like this:

```
chocolate-doom -merge thetc.wad
```

Here are some examples:

```
chocolate-doom -merge batman.wad -deh batman.deh vbatman.deh  (Batman Doom)
chocolate-doom -merge aoddoom1.wad -deh aoddoom1.deh  (Army of Darkness Doom)
```

## Other information

 * Chocolate Doom includes a number of different options for music
   playback. See the README.Music file for more details.

 * More information, including information about how to play various
   classic TCs, is available on the Chocolate Doom website:

     https://www.chocolate-doom.org/

   You are encouraged to sign up and contribute any useful information
   you may have regarding the port!

 * Chocolate Doom is not perfect. Although it aims to accurately
   emulate and reproduce the DOS executables, some behavior can be very
   difficult to reproduce. Because of the nature of the project, you
   may also encounter Vanilla Doom bugs; these are intentionally
   present; see the NOT-BUGS file for more information.

   New bug reports can be submitted to the issue tracker on Github:

     https://github.com/chocolate-doom/chocolate-doom/issues

 * Source code patches are welcome, but please follow the style
   guidelines - see the file named HACKING included with the source
   distribution.

 * Chocolate Doom is distributed under the GNU GPL. See the COPYING
   file for more information.

 * Please send any feedback, questions or suggestions to
   chocolate-doom-dev-list@chocolate-doom.org. Thanks!



