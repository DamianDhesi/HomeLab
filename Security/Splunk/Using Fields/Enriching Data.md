can store an eval command to perform an eval operation every time the relevant fields in the command are found in a search
- best to use field names in command and not aliases as they may not be assigned in a specific search
	- alternatively can create permanent aliases so aliases can be referenced in searches and commands

## Lookups
include fields not in indexed data

## Search Operation Ordering
1. field extractions
2. field aliases
3. calculated fields
4. lookups
5. event types
6. tags

alias can't reference calculated fields as that operation happens later but calculated fields can reference aliases