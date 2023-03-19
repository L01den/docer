## Задание 1

lorden@zt:/usr/share/lxc/templates$ sudo lxc-create -n test0 -t download
Downloading the image index

DIST	RELEASE	ARCH	VARIANT	BUILD...(рис. 1)

Distribution:

ubuntu

Release:

jammy

Architecture:

amd64


Downloading the image index

Downloading the rootfs

Downloading the metadata

The image cache is now ready

Unpacking the rootfs



You just created an Ubuntu jammy amd64 (20230318_07:42) container.

To enable SSH, run: apt install openssh-server
No default root or user password are set by LXC.(рис. 2)

## Задание 2

nano config (рис. 3)

Для ограничения памяти прописать в конфиге: *lxc.cgroupe2.memory.max = 256M*, сохранить перед выходом.

Для проверки надо зайти в контейнер командами:

root@zt:/var/lib/lxc# lxc-start -n test0

root@zt:/var/lib/lxc# lxc-attach -n test0

root@test0:/# free -m(рис. 3)

## Задание 3
Для автозапуска контейнере прописать в конфиге: *lxc.start.auto = 1*(рис. 3).

## Задание 4 и 5

root@zt:/usr/share/lxc/templates# lxc-start -n test0 --logfile /log.log

root@zt:/usr/share/lxc/templates# cd /

root@zt:/# lxc-start -n test0 --logfile /log.log -d

lxc-start: test0: tools/lxc_start.c: main: 256 Container is already running

root@zt:/# cat log.log
lxc-start test0 20230319081330.942 ERROR    lxc_start - tools/lxc_start.c:main:256 - Container is already running






