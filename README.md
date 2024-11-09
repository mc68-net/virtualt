VirtualT with Fixes
===================

The [Virtual T][sf-main] project on SourceForge is a TRS-80 Model
100/102/200 emulator that runs on Windows, Linux and Mac. This is
a fork of its [git repo][sf-git].

The `fixes` branch of this repo includes, as of this writing, everything
from the `master` branch of the upstream repo, plus fixes. This currently
includes:

* A fix conflicting definitions of `path` in `src/m100emu.cpp` and
  `src/linker.cpp` that breaks the build on Linux (or at least Debian
  flavours of it), producing a "multiple definition of 'path'" error from
  `ldd`. (The fix is taken straight from [bug report 9][sf-bug-9], which
  was submitted in 2022.)

The `main` branch of this repo has nothing on it but this README.


Building and Using VirtualT on Linux
------------------------------------

These notes are supplementary to the "Chapter 1 - Build and Install"
document (`doc/build.html`) in the sources.

### Building

Debian provides two versions of the FLTK library, so you do not need to
build it yourself. The instructions specify version 1.1 of the library
(available as `libfltk1.1-dev`), but for VirtualT 1.8, `libfltk1.3-dev`
seems to work fine. There are also some other libraries you'll need:

    sudo apt install build-essential libxft-dev libxinerama-dev 
        libfontconfig-dev libjpeg-dev libfltk1.3-dev

The build produces many warnings.

### Running

`virtualt` depends on having various files available under the current
working directory (CWD) when it's executed, and will create further
directories and files in the CWD.

On the first start, the ROM images must be available under `./ROMs/`; the
source distribution contains a `ROMs/` directory with everything you need.
If any files are missing, you will receive a warning dialogue, but can
continue so long as you have the files you need for the particular machine
you requested.

Also on first start, the following directories will be created:

    ./KC85/  ./M10/  ./M100/  ./M102/  ./PC8201/  ./PC8300/  ./T200/

The matching files from `./ROMs/` will be copied into the subdirectories;
any missing ones on subsequent startups will attempt to be copied again
from `./ROMs/` and a warning dialogue will be produced.



<!-------------------------------------------------------------------->
[sf-git]: https://git.code.sf.net/p/virtualt/code.git
[sf-main]: https://sourceforge.net/projects/virtualt/
[sf-bug-9]: https://sourceforge.net/p/virtualt/bugs/9/
