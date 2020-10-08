# my.cnf.templates
Optimized my.cnf configuration templates compatible with MySQL 5.x and MariaDB 10.x.

The templates includes configurations for standard RAM sizes from 1 GB to 48 GB. The script `update-my-cnf-template` can build configurations for non-standard RAM sizes using a similar available template, and adjust variables based on the number of CPU cores too.


### Notes for systemd
Some MySQL limits cannot be applied using `my.cnf` only. We may need to specify an upper limit via `/etc/systemd/system/mysqld.service.d/systemd-limits.conf`, `/etc/systemd/system/mysql.service.d/systemd-limits.conf` or `/etc/systemd/system/mariadb.service.d/systemd-limits.conf` and run `/bin/systemctl daemon-reload` to load our custom limit conf.

### Sample output
```
# update-my-cnf-template 
INFO: Template directory set to /etc/my.cnf.templates
DEBUG: CNF_VERSION=20200613, TMPL_VERSION=20200730, SYS_RAM=12, CNF_RAM=8
WARNING: Template needs update
‘/etc/my.cnf’ -> ‘/etc/my.cnf.previous’
‘/etc/my.cnf.templates/my.cnf_12gb’ -> ‘/etc/my.cnf’
Fine-tuning some variables matching with 12 GB RAM and 6 CPU cores
Retaining custom values
Please manually restart MySQL service to apply changes

# update-my-cnf-template 
INFO: Template directory set to /etc/my.cnf.templates
DEBUG: CNF_VERSION=20200730, TMPL_VERSION=20200730, SYS_RAM=12, CNF_RAM=12
INFO: Template is up-to-date
INFO: Template not applied
```
