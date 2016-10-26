# dns-airprint
Airprint over Bind DNS script.

In bind db.SITE file you need to add at the top
```
printserver                     IN      A       123.123.123.123   ; the CUPS server IP

b._dns-sd._udp                  IN      PTR     @
lb._dns-sd._udp                 IN      PTR     @
```
Then generate printer entries with the script.  -H CUPS server.
```
dns-airprint.py -H 123.123.123.123
```
Copy and paste the results into db.SITE file.


This script is based on airprint-generate.py for bind instead of avahi:
https://github.com/tjfontaine/airprint-generate

