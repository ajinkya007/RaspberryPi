##Installation of Whatsapp in RPI  

###Step 1:- Installation of necessary packages

To use WhatsApp on Raspberry Pi we will need Yowsup which is a Python library that lets you access all the functionalities of WhatsApp on Raspberry Pi just as you would from the official client app on your smartphone. Update the RPi to the latest version.
Command :- 
```
sudo rpi-update
```

To install Yowsup we need to install certain packages. As apt is the package manager in Raspbian we can use the apt-get install tool to install packages.

Commands :-
```
sudo apt-get install python-dateutil  

sudo apt-get install python-setuptools  

sudo apt-get install python-dev  

sudo apt-get install libevent-dev  

sudo apt-get install ncurses-dev  
```

The Yowsup library can then be downloaded.

Command :- 
```
git clone git://github.com/tgalal/yowsup.git
```
Use cd command to get into the Yowsup folder and install the library.

Commands :-
``
cd yowsup  

sudo python setup.py install  
```
