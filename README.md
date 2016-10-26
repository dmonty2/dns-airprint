# dns-airprint
Airprint over Bind DNS script.

In bind /etc/bind/db.SITE file you need to add at the top (where SITE is your zone)
```
printserver                     IN      A       123.123.123.123   ; the CUPS server IP

b._dns-sd._udp                  IN      PTR     @
lb._dns-sd._udp                 IN      PTR     @
```
Then auto-generate printer entries with the script.  Change IP to match your cups server IP/hostname.
```
dns-airprint.py -H 123.123.123.123
```
Copy and paste the results into /etc/bind/db.SITE file.


This script is based on Timothy Fontaine's airprint-generate.py for bind instead of avahi:
https://github.com/tjfontaine/airprint-generate

