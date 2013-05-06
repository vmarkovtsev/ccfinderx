CCFinderX
=========

This is a clone of [CCFinderX][1] that has the settings to build with autoconf on a Linux machine.

The autoconf setting is not finished (it does not pass `make distcheck`), but it is something to start with. The process to build `ccfinderx` is:

    $ libtoolize
    $ aclocal -I m4 --install
    $ autoconf
    $ automake --foreign --add-missing
    $ mkdir build && cd build && ../configure
    $ make -j$(getconf _NPROCESSORS_ONLN)

If there is an error in make `ccfinderx_CCFinderX.h`, then is necessary to generate it via:

    $ cd GemX
    $ make ccfinderx_CCFinderX_h

To build GemX (the graphical user interface):

    $ cd GemX
    $ make

Ubuntu packages needed to successfully build the project (may not be complete):

sudo apt-get install libboost-system1.53-dev libboost-thread1.53-dev python2.7-dev openjdk-7-jdk libicu-dev

  [1]: http://www.ccfinder.net/ccfinderxos.html
