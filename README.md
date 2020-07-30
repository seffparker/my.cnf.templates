# my.cnf.templates
Optimized my.cnf configuration templates compatible with MySQL 5.x and MariaDB 10.x.

The templates includes configurations for standard RAM sizes from 1 GB to 48 GB. The script `update-my-cnf-template` can build configurations for non-standard RAM sizes using a similar available template, and adjust variables based on the number of CPU cores too.


### Notes for systemd
Some MySQL limits cannot be applied using `my.cnf` only. We may need to specify an upper limit via `/etc/systemd/system/mysqld.service.d/systemd-limits.conf`, `/etc/systemd/system/mysql.service.d/systemd-limits.conf` or `/etc/systemd/system/mariadb.service.d/systemd-limits.conf` and run `/bin/systemctl daemon-reload` to load our custom limit conf.
