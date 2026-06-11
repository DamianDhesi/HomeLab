get the .crt file to the linux host (download, copy from usb, etc.)
- can use "--insecure" to ignore tls/ssl warnings with curl

move the file to the local CA directory
```
mv <crt_file> /usr/local/share/ca-certificates/
```

update trusted CAs
```
update-ca-certificates
```