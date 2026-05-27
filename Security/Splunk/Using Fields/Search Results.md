some fields are extracted during index ingestion (source, host, sourcetype, etc.) at search times more fields are extracted based on sourcetype and key value pairs

## Temp Fields
can use eval to performs some type of operation on fields

ex:
```
... | eval bandwidth = Bytes/1024/1024
```
- creates a bandwidth field that calculates the number of MB using the Bytes field

## Field Extraction
can extract fields that were not extracted at source time using field extractor

can use erex, rex to extract fields using regex automatically (don't need to know regex)
ex:
```
... | erex Character fromfield=_raw examples="pixie, Kooby"
```
- only knows what to look for based on examples given

can use rex for manual regex setup
ex:
```
... | field=_raw "<regex_expression>"
```
