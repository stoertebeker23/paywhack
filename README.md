# paywhack
Proposed payment system. It was written by @olf42 

## Barcode scanner

### Device
We use a Datalogic 8200 Omega as Barcode scanner. It puts out the barcode in serial. 
A microcontroller reading the serial output registers as a USB Keyboard and is plugged into the server.
Any USB Barcodescanner should be useable, some of them print a prefix, which in our case is 'F'. This prefix is specified 
in the constants.py.

### Device is not running
Check if the lights are glowing or the motor is running (sounds like a fan). If not, hit the volume button and it should wake up. Otherwise check the power cable.

## Printer
A receipt printer is used to print out the user receipts. They contain a barcode registered in the database and connected to a username. 

### How to change ip for the printer
Our printer has a static ip so if it is connected directly to the ethernet port of the server, you need to change the ip range of the server.
```
ip addr add 192.168.0.1/24 dev [network port]
```
Printer should have a static 192.168.0.10
Test with
```
ping 192.168.0.10
```

### Activate printing
Change this line in constants.py to activate printing out receipts
```
PRINT_ENABLED = False
```

### Install tcl8.6 and tcl8.6dev
Found in the ubuntu repositories
```
sudo apt-get install tcl8.6 tcl8.6-dev
```

### Compile tcl.gd against tcl8.6
Therefor check the Readme of inside the tcl.gd folder in the root directory
It contains the ./configure arguments. 

### Distro
The tcl package does not work on xubuntu 16.10. It works under Ubuntu16.04.

## Server

### Use chromium
Firefox somehow doesn't get all the scans and sometimes it takes multiple scans to get a product into the cart.
```
sudo apt-get install chromium-browser
```

### Open the right port in browser
It is 8025 by default, but can be configured in run_server.py

### Pyhton requirements
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
### Launch
Start the paywhack server
```
python3 run_server.py
```
Start the print service
```
python3 escpos_server.py
```
