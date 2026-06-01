## Installing Sysmon
[download sysmon](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon)

good base config for sysmon is the one from [SwiftOnSecurity](https://github.com/SwiftOnSecurity/sysmon-config)

use it for installing sysmon as so
```
./sysmon -i ./sysmonconfig-export.xml -accepteula
```

sysmon logs will now start appearing in Applications and Services Logs/Microsoft/Windows/Sysmon/Operational when using event viewer
- can easily test by pinging an ip to get a network connection log

## Forwarding Sysmon logs to Splunk
Need [Splunk's sysmon add on](https://splunkbase.splunk.com/app/5709) installed on the indexer in order to properly parse sysmon events

edit /etc/apps/SplunkUniversalForwarder/local/inputs.conf of the universal forwarder to set the up the forwarder to send sysmon logs to splunk

add the following to the inputs.conf file
```
[WinEventLog://Microsoft-Windows-Sysmon/Operational]
checkpointInterval = 5
current_only = 0
disabled = 0
start_from = oldest
```

restart the forwarder and sysmon logs should now start showing up in the splunk indexer
- search with 
	- sourcetype="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
