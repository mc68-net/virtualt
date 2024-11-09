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



<!-------------------------------------------------------------------->
[sf-git]: https://git.code.sf.net/p/virtualt/code.git
[sf-main]: https://sourceforge.net/projects/virtualt/
[sf-bug-9]: https://sourceforge.net/p/virtualt/bugs/9/
