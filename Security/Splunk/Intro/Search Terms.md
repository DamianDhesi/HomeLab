has wildcard searches
ex:
```
fail*
```
- for anything with starting with fail

search terms are non-case sensitive

can use Booleans
- AND
	- used by default if multiple terms listed
- OR
- NOT
- order of eval is
	- NOT -> OR -> AND
	- can use parenthesis to change order of eval

exact phrase can be used by putting terms in quotes
```
"failed password"
```
- only events with the string "failed password" will show up
- can use \ to escape quotes
```
"user \"john\" in database"
```