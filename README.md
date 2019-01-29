# change-mac
Small script to change MAC addresses on Windows.

Further info can be found in this [blog post about MAC addresses](https://inc0x0.com/2019/01/changing-mac-address-windows/).




## Binaries
Compatible with Win 7/Vista/8/10 32/64bit, get them from the [release section](https://github.com/inc0x0/change-mac/releases).

If you want to create your own executable, generate it with [Pyinstaller](https://www.pyinstaller.org/) on a Win7 32bit system:
```
pyinstaller change-mac.py -F --clean
```

## How to use change-mac
CMD or PowerShell with administrative privileges. Most use cases can be found in the 'Example usage' section:
```
change-mac.py -h

usage: change-mac.exe [-h] [-l] [-r] [-i INTERFACE] [-m MAC] [-f]

A small script to change MAC addresses in Windows

optional arguments:
  -h, --help            show this help message and exit
  -l, --list            list all network interfaces
  -r, --reset           reset MAC address of the provided network interface to
                        default
  -i INTERFACE, --interface INTERFACE
                        provide an interface GUID (part of the "Transport
                        Name"), e.g. CA8D7884-4754-4E6D-B637-D411533ECBBA
  -m MAC, --mac MAC     provide a valid MAC address, e.g. 00:0C:29:FE:8B:77.
                        Might need 02 as the first octet for Wifi.
  -f, --force           force restart network interface

Note:
WiFi Connections might need a 02 as first octet, e.g. 02:xx:xx:xx:xx:xx

Example usage:
change-mac.exe -l
change-mac.exe -i CA8D7884-4754-4E6D-B637-D411533ECBBA -m 00:0C:29:FE:8B:77
change-mac.exe -i CA8D7884-4754-4E6D-B637-D411533ECBBA -m 00:0C:29:FE:8B:77 -f
change-mac.exe -i CA8D7884-4754-4E6D-B637-D411533ECBBA -r
change-mac.exe -i CA8D7884-4754-4E6D-B637-D411533ECBBA -f
change-mac.exe -i CA8D7884-4754-4E6D-B637-D411533ECBBA -r -f
```
