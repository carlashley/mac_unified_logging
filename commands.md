### Show commands executed with `sudo` in the last 20min
log show --style syslog --info --backtrace --debug --signpost --force --predicate 'process == "sudo" && composedMessage CONTAINS "COMMAND="' --last 20m

### Show AirDrop events - using JSON styling for log shipping
log show --style json --info --backtrace --debug --signpost --force --predicate 'subsystem == "com.apple.sharing" AND category == "AirDrop"' --last 20m
