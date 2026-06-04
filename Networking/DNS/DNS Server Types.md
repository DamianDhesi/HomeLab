## Recursive
When a query is sent the DNS server the server will first check its cache to see if it has the ip for the respective DNS saved, if not, the server will recursively query DNS servers until it receives an ip or there is a failure

DNS recursive query order:
1. root servers, of which there are 13 (".")
2. top level domain (TLD) server (".com")
3. domain server ("microsoft.com")
4. sub domain server ("azure.microsoft.com")
can fail recursive query if things time out and such, which is normal, but should be low (<10%)
- server failures will improve as cache is filled

when to use
- good if you want privacy regarding DNS queries for hosts, though there is not technically full privacy regarding the recursive DNS query resolution itself (root servers don't support encryption, as of writing)
## Authoritative
dns server that is authoritative (specifically configured to administer) for a DNS zone (ex: micrsoft.com)
- generally trustworthy for the DNS zone it covers
- will only return answers about queries relating to DNS zone
- may point to a secondary DNS server for sub domains and such

when to use
- need when hosting a DNS zone (ex: microsoft.com)
	- can't have DNS resolution for a domain you own without one
## Forwarder
will forward queries to another DNS server if it does not find the domain ip in its cache
- ex: could forward requests to a recursive dns like 8.8.8.8

when to use
- nice when you want faster DNS resolution and don't mind any privacy concerns around the target DNS server being aware of DNS queries
