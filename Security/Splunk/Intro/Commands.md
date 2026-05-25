how searching works
- search terms
	- used for queries
- commands say what to do with search results 
	- charts
	- stats
	- formating
	- etc.
- functions
	- how to eval/chart result
- Arguments
	- vars to apply to function
- clause 
	- how to group/define results

ex:
```
index=network sourcetype=cisco_wsa_squid usage=Violation | stats count(usage) as Visits
```
- search terms
	- index=network sourcetype=cisco_wsa_squid usage=Violation
- command
	- stats
- function
	- count()
- argument
	- usage
- clause
	- as
- what it does
	- gets events involving usage violations from a specific source in the network index. Then takes is data counts all usage violations and records that in the visits field

can split aggregated results by fields using the "by" clause
```
... as Visits by cs_username
```
- gets visit count for each user


can use search command for further result filtering
```
... | search Visits > 1
```
- find all results where Visits field is greater than 1

## Best Practice
best to filter by
- time
- index
- source
- host
- sourcetype
in order to reduce time to compile results 
- better results the more specific you get