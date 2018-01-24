To enable UART on the Raspberry Pi 3 via the GPIO Pins:

1, open terminal, log in, then type:

sudo nano /boot/config.txt

Add the line at the bottom:

core_freq=250
enable_uart=1

save your changes and reboot for changes to take effect.

2, Disable the Console:

sudo systemctl stop serial-getty@ttyS0.service
sudo systemctl disable serial-getty@ttyS0.service

sudo nano /boot/cmdline.txt

remove the line: console=serial0,115200

save your changes and reboot for changes to take effect.



Install The Flow:

Open FLOW_1.txt, Select All, Copy

Open Node-Red in your browser and click on the 3 horizontal bars at the top right of the screen.
Hover your mouse over Import, then click Clipboard.
Paste the code into the window, make sure 'new flow' is selected, then click Import.
Double click on the function GSM M590E.
Here you will see:

global.set("Phone_Number","YOUR_NUMBER_HERE");

Replace YOUR_NUMBER_HERE with the phone number you want the text to go to.

ie. +447890112233


so replace the zero at the begining of your destination number with +44 

+44 is the code for United Kingdom

+61 is the code for Australia

+1 United States of America

etc...

This sets a global variable with your phone number so that all other functions do not have to be modified.

This code uses the default settings on your GSM Module

*** Serial Settings ***



Serial Port: /dev/ttyAMA0


Connection:


Baud Rate: 115200

Data Bits: 8

Parity: None

Stop Bits: 1



Input:


Split Input: after timeout of, 500ms

And Deliver: ascii strings



***********************

Then Deploy

hope this works for you.... took me a few days to get this to work.