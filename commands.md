# Show commands executed with `sudo` in the last 20min
log show --style syslog --info --backtrace --debug --signpost --force --predicate 'process == "sudo" && composedMessage CONTAINS "COMMAND="' --last 20m
