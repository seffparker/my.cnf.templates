# my.cnf.templates
Optimized my.cnf configuration templates compatible with MySQL 5.x and MariaDB 10.x.

<<<<<<< HEAD
The templates includes configurations for standard RAM sizes from 1 GB to 48 GB. The script `update-my-cnf-template` can build configurations for non-standard RAM sizes using a similar available template, and adjust variables based on the number of CPU cores too.
=======
The templates includes configurations for standard RAM sizes from 1 GB to 48 GB. The script `update-my-cnf-template` can build configurations for non-standard RAM sizes using a similar avaiable template, and adjust variables based on the number of CPU cores too.
>>>>>>> 9c72ec777ca1a217c3dddbd26923b05f4762007f


### Note for systemd
Some limits cannot be applied using `my.cnf` only. We may need to specify an upper limit via `/etc/systemd/system/mysqld.service.d/systemd-limits.conf`:
```
[Service]
LimitNOFILE=65535
LimitMEMLOCK=infinity
```
and run `/bin/systemctl daemon-reload` to load our custom limits.
<<<<<<< HEAD

=======
>>>>>>> 9c72ec777ca1a217c3dddbd26923b05f4762007f
