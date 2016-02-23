# Build Kernel

```shell
cd /usr/src/linux-3.X

make mrproper

cp /boot/config-$(uname -r) .config

make menuconfig
     
make-kpkg -j4 --append-to-version=-x64 --initrd kernel_image kernel_headers
```

errors
```shell
# make menuconfig
  HOSTCC  scripts/basic/fixdep
  HOSTCC  scripts/kconfig/mconf.o
In file included from scripts/kconfig/mconf.c:23:0:
scripts/kconfig/lxdialog/dialog.h:38:20: fatal error: curses.h: Datei oder Verzeichnis nicht gefunden
 #include CURSES_LOC
                    ^
compilation terminated.
scripts/Makefile.host:108: recipe for target 'scripts/kconfig/mconf.o' failed
make[1]: *** [scripts/kconfig/mconf.o] Error 1
Makefile:531: recipe for target 'menuconfig' failed
make: *** [menuconfig] Error 2
```

solution
```shell
apt-get install libncurses5-dev
```

rather tools
```shell
apt-get install initramfs-tools cramfsprogs kernel-package
```

