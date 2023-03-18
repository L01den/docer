lorden@zt:~$ sudo unshare --net /bin/bash

lorden@zt:~$ sudo unshare --net -- pid /bin/bash

unshare: невозможно выполнить pid: Нет такого файла или каталога

lorden@zt:~$ sudo unshare --net --pid /bin/bash

bash: fork: Невозможно выделить память

root@zt:/home/lorden# exit

exit

lorden@zt:~$ sudo unshare --net --pid --fork /bin/bash

root@zt:/home/lorden# exit

exit

lorden@zt:~$ sudo unshare --net --pid --fork --mount-proc /bin/bash

root@zt:/home/lorden# ps -aux

USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND

root           1  0.0  0.0  18888  4160 pts/1    S    10:40   0:00 /bin/bash

root           8  0.0  0.0  21620  3800 pts/1    R+   10:41   0:00 ps -aux

root@zt:/home/lorden# exit

exit




