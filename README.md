# paywhack
Proposed payment system. It is mainly written by @olf42 

## How to change ip for the printer
```
ip addr add 192.168.0.1/24 dev [network port]
```
Printer should have a static 192.168.0.10
Test with
```
ping 192.168.0.10
```

## Activate printing
Go to constants.py and set printing=true

## Install tcl8.6 and tcl8.6dev
Found in the repositories
```
sudo apt-get install tcl8.6 tcl8.6-dev
```

## Compile against tcl8.6
Therefor check the Readme of inside the tcl.gd folder in the root directory
It contains the ./configure arguments. 

## Check if the barcodescanner works
Microcontroller should be powered, usb connected, motor running. If not hit the volume button on the printer.

## Use chromium
Firefox somehow doesn't get all the scans and sometimes it takes multiple scans to get a product into the cart.
```
sudo apt-get install chromium-browser
```

## Open the right port in browser
It should be 8025, but can be configured in the code

## Pyhton requirements
Install python3
```
sudo apt-get install pyhton3
```
Install pip3
```
sudo apt-get install python3-pip
```
Then do: 
```
pip3 install -r requirements.txt
```

## Distro
The tcl package does not work on xubuntu 16.10. It works under Ubuntu16.04

## Launch
Start the paywhack server
```
python3 run_server.py
```
Start the print service
```
python3 escpos_server.py
```
