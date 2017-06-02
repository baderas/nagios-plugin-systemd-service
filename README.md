# nagios-plugin-systemd-timer

Nagios plugin to check the status of a systemd service that is regularly started by a montonic timer.

E.g. check if a job is started every 2 hours and exited sucessfully.

## Authors

Mohamed El Morabity <melmorabity -(at)- fedoraproject.org> (nagios-plugin-systemd-service)

Andreas Bader <development -(at)- geekparadise.de> (nagios-plugin-systemd-timer)

## Usage

    check_systemd_timer.sh <service name> <timer name> <time in seconds between runs that is not warning> <time in seconds between runs thar is not critical>

## Examples

    $ ./check_systemd_timer.sh <some service> <some timer> 3200 7200
    OK: service <some service>.service was running 1250 seconds ago.

     $ ./check_systemd_service.sh <some bad service> <some timer> 3200 7200
    ERROR: service <some service>.service was executed 900 seconds ago and exited with status error."

     $ ./check_systemd_service.sh <some service> <some bad timer> 3200 7200
    WARNING: service <some service>.service was executed 3300 seconds ago."

    $ ./check_systemd_service.sh <some service> <some bad timer> 3200 7200
    ERROR: service <some service>.service was executed 7300 seconds ago."

    $ ./check_systemd_service.sh <not existing service> <some timer> 3200 7200
    ERROR: service <not existing service>.service doesn't exist
    
    $ ./check_systemd_service.sh <some service> <not existing timer> 3200 7200
    ERROR: timer <not existing timer>.timer doesn't exist
