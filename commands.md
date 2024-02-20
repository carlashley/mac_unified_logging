### Show commands executed with `sudo` in the last 20min
log show --style syslog --info --backtrace --debug --signpost --force --predicate 'process == "sudo" && composedMessage CONTAINS "COMMAND="' --last 20m

### Show AirDrop events - using JSON styling for log shipping
log show --style json --info --backtrace --debug --signpost --force --predicate 'subsystem == "com.apple.sharing" AND category == "AirDrop"' --last 20m

## Software Update DDM
﻿log show --info --debug --predicate 'process = "SoftwareUpdateSubscriber" && eventMessage CONTAINS[cd] "Reporting status"' --style compact --last 1h
log show --info --debug --predicate '((subsystem CONTAINS[cd] "com.apple.remotemanagementd") || (subsystem CONTAINS[cd] "RemoteManagement") || (processImagePath CONTAINS[cd] "RemoteManagement.framework"))' --last 1h
