To enable UART on the Raspberry Pi Zero via the GPIO Pins:

open terminal, log in, then type:

sudo nano /boot/cmdline.txt

Then comment out the original line with # and add the next line.
This will allow you to use the serial with Node-Red or any other software.

#dwc_otg.lpm_enable=0 console=serial0,115200 console=tty1 root=/dev/mmcblk0p2 rootfstype=ext4 elevator=deadline fsck.repair=yes rootwait
dwc_otg.lpm_enable=0 console=tty1 root=/dev/mmcblk0p2 rootfstype=ext4 elevator=deadline fsck.repair=yes rootwait



Install The Flow:

Open FLOW_1.txt, Select All, Copy

Open Node-Red in your browser and click on the 3 horizontal bars at the top right of the screen.
Hover your mouse over Import, then click Clipboard.
Paste the code into the window, make sure 'new flow' is selected, then click Import.
Double click on the function near the top left of the flow that says Phone Number.
Here you will see:

global.set("Phone_Number","YOUR NUMBER HERE");

Replace YOUR NUMBER HERE with the phone number you want the text to go to.
This sets a global variable with your phone number so that all other functions do not have to be modified.

Then Deploy

hope this works for you.... took me a few days to get this to work.