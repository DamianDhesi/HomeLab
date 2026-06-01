```
souretype="...Sysmon/Operational" Eventcode=1 | join type=inner left=L right=R L.ProcessGuid = R.ProcessGuid [search sourcetype="...Sysmon/Operational" Eventcode=13]
```