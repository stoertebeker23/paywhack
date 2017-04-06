# paywhack
Proposed payment system. It is mainly written by @olf42 

## How to change ip for the printer
ip addr add 192.168.0.1/24 dev [network port]
Printer should have a static 192.168.0.10

## Activate printing
Go to constants.py and set printing=true

## Install tcl8.6 and tcl8.6dev
Found in the repositories

## Compile against tcl8.6
Therefor check the Readme of inside the tcl.gd folder in the root directory
It contains the ./configure arguments. 

## Check if the barcodescanner works
Microcontroller should be powered, usb connected, motor running. If not hit the volume button on the printer.

## Use chromium
Firefox somehow doesn't get all the scans and sometimes it takes multiple scans to get a product into the cart.

