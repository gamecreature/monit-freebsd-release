# Monit FreeBSD Release Check

This is a monit script to monitor the FreeBSD release version.
It only needs to be schedule once a day to check if the system is still up to date.
The script will make monit alert, when there's a new FreeBSD release available.

The script is based on the script of @mkhon: https://github.com/mkhon/zabbix-freebsd-release.

## Installation

1. Copy the `freebsd_release_check.sh` script to `/usr/local/etc/monit.d/scripts`

2. Copy the `freebsd_release.conf` script to `/usr/local/etc/monit.d/freebsd_release.conf`. And configure it to your requirements!

## Note

The example `freebsd_release.conf` monit script runs the test every `172800` cycles.
This means daily for a 30 second per cycle interval.  The cron syntax would be much nicer, but there isn't a guarantee it will run:

https://mmonit.com/monit/documentation/monit.html#SERVICE-POLL-TIME

> *Therefore we strongly recommend to use an asterix in the minute field or at minimum a range, e..g. 0-15. Never use a specific minute as Monit may not run on that minute.*
