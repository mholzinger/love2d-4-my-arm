# love2d-4-my-arm

## Compiled library and executable files for the open source love2d project built on RaspberryPi

Project files for the precompiled love source are located at:

https://github.com/mholzinger/love2d-4-my-arm/compiled-src/

Debian skeleton files are located at:

https://github.com/mholzinger/love2d-4-my-arm/deb-skel/

These projects were compiled on a RaspberryPi 3B running Ubuntu Mate (Ubuntu 16.04.4 LTS)

---

## Steps to compile Love2D source from the https://love2d.org/ project for arm

- Install love dependencies

Dependency note:

*deb-src must be enabled in `/etc/apt/sources.list`*

```deb-src http://raspbian.raspberrypi.org/raspbian/ stretch main contrib non-free rpi```

- Update raspbian

```
sudo apt-get update
sudo apt-get install libtheora-dev
sudo apt-get build-dep love
```

- Grab the latest source for love (11.1)

```
wget  https://bitbucket.org/rude/love/downloads/love-11.1-linux-src.tar.gz
tar xvf love-11.1-linux-src.tar.gz
cd love-11.1
```

- Build love!

```
./configure
make
sudo make install
```

Make install output:

```
$ sudo make install
Making install in src
make[1]: Entering directory '/home/pi/src/love-11.1/src'
make[2]: Entering directory '/home/pi/src/love-11.1/src'
make[3]: Entering directory '/home/pi/src/love-11.1/src'
 /bin/mkdir -p '/usr/lib'
 /bin/bash ../libtool   --mode=install /usr/bin/install -c   liblove.la '/usr/lib'
libtool: install: /usr/bin/install -c .libs/liblove-11.1.so /usr/lib/liblove-11.1.so
libtool: install: (cd /usr/lib && { ln -s -f liblove-11.1.so liblove.so || { rm -f liblove.so && ln -s liblove-11.1.so liblove.so; }; })
libtool: install: /usr/bin/install -c .libs/liblove.lai /usr/lib/liblove.la
libtool: finish: PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/sbin" ldconfig -n /usr/lib
----------------------------------------------------------------------
Libraries have been installed in:
   /usr/lib

If you ever happen to want to link against installed libraries
in a given directory, LIBDIR, you must either use libtool, and
specify the full pathname of the library, or use the '-LLIBDIR'
flag during linking and do at least one of the following:
   - add LIBDIR to the 'LD_LIBRARY_PATH' environment variable
     during execution
   - add LIBDIR to the 'LD_RUN_PATH' environment variable
     during linking
   - use the '-Wl,-rpath -Wl,LIBDIR' linker flag
   - have your system administrator add LIBDIR to '/etc/ld.so.conf'

See any operating system documentation about shared libraries for
more information, such as the ld(1) and ld.so(8) manual pages.
----------------------------------------------------------------------
 /bin/mkdir -p '/usr/bin'
  /bin/bash ../libtool   --mode=install /usr/bin/install -c love '/usr/bin'
libtool: install: /usr/bin/install -c .libs/love /usr/bin/love
make[3]: Nothing to be done for 'install-data-am'.
make[3]: Leaving directory '/home/pi/src/love-11.1/src'
make[2]: Leaving directory '/home/pi/src/love-11.1/src'
make[1]: Leaving directory '/home/pi/src/love-11.1/src'
make[1]: Entering directory '/home/pi/src/love-11.1'
make[2]: Entering directory '/home/pi/src/love-11.1'
make[2]: Nothing to be done for 'install-exec-am'.
 /bin/mkdir -p '/usr/share/applications'
 /usr/bin/install -c -m 644 platform/unix/love.desktop '/usr/share/applications'
 /bin/mkdir -p '/usr/share/icons/hicolor/scalable/mimetypes'
 /usr/bin/install -c -m 644 platform/unix/application-x-love-game.svg '/usr/share/icons/hicolor/scalable/mimetypes'
 /bin/mkdir -p '/usr/share/mime/packages'
 /usr/bin/install -c -m 644 platform/unix/love.xml '/usr/share/mime/packages'
 /bin/mkdir -p '/usr/share/pixmaps'
 /usr/bin/install -c -m 644 platform/unix/love.svg '/usr/share/pixmaps'
 /bin/mkdir -p '/usr/share/man/man1'
 /usr/bin/install -c -m 644 'platform/unix/love.6' '/usr/share/man/man1/love.1'
make[2]: Leaving directory '/home/pi/src/love-11.1'
make[1]: Leaving directory '/home/pi/src/love-11.1'
```
