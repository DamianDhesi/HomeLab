can use the following as operators with fields
- =
- !=
- >
- >=
- <
- <=
- ex: index=security
- ex: host!="mail*"

can click on field in fields menu to add it to the search

## NOT vs !=
```
status!=200
```
- returns all events where the status field is not 200

```
NOT status=200
```
- returns all events that don't have a status field of 200
- **includes events without a status field at all** 

## IN
instead of 
```
status=500 OR status=501 OR ...
```
you can do
```
status IN ("500", "501", etc.)
```

## Fields Command
include field via
```
... | field +status
```
or
```
... | field status
```

exclude field via
```
... | field -status
```

## Rename
rename a field
```
... | rename status as "HTTP Status", count as "Number of Events"
```
