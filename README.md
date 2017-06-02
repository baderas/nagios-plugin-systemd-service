# nagios-plugin-systemd-timer

Nagios plugin to check the status of a systemd service that is regularly started by a montonic timer.

E.g. check if a job is started every 2 hours and exited sucessfully.

## Authors

Mohamed El Morabity <melmorabity -(at)- fedoraproject.org> (nagios-plugin-systemd-service)

Andreas Bader <development -(at)- geekparadise.de> (nagios-plugin-systemd-timer)

## Usage

    check_systemd_timer.sh <service name> <time in seconds between runs that is not warning> <time in seconds between runs thar is not critical>

## Examples

    $ ./check_systemd_timer.sh sshd
    OK: service sshd is running

    $ sudo systemctl stop sshd
    $ ./check_systemd_service.sh sshd
    ERROR: service sshd is not running

    $ ./check_systemd_service.sh foo
    ERROR: service foo doesn't exist
