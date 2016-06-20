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

###Step 2 :- WhatsApp registration

To register with WhatsApp you do not have a GUI but you can make use of a command line utility provided by Yowsup – yowsup-cli. To use it you need to know your country code(cc), mobile country code(mcc) and mobile network code(mnc). You may be familiar with the country code which you see in the beginning of phone numbers. To find mcc and mnc visit the link below.

Command :- 
```
python yowsup-cli registration --requestcode sms --phone 91xxxxxxxxxx --cc 91 --mcc 405 --mnc 035
```

While entering phone number keep in mind that you can use WhatsApp for one number on one device only. Do not use a number that you use for you daily WhatsApp messaging.

You will receive a code like your normal WhatsApp registration process. Send back this code using the following command. The code is to be entered by replacing the 'x's after register.

Command :- 
```
python yowsup-cli registration --register xxx-xxx --phone 91xxxxxxxxxx --cc 91
```
If your registration is successful you will get a confirmation message.

###Step 3:- Using WhatsApp

To use WhatsApp you will need to enter your phone number and password. You can save them on a config file inside the Yowsup folder. Use nano, a command line text editor for the same.

Command :- 
```
sudo nano /home/pi/yowsup/config
```

Add the following lines into the config file.

Actual config starts below: 

  cc=39 #if not specified it will be autodetected

  phone=39xxxxxxxxxx

  password=xxxxxxxxxxxxxxx

To begin using WhatsApp use the yowsup-cli demo.

Command :- 
```
yowsup-cli demos --yowsup --config config
```

You will be greeted with the Yowsup prompt. To login you may enter '/L' and enter your login credentials you saved in the config file. You can see a list of commands by typing '/help'. Use the /message command to send a message to your desired number.

Command :- 
```
/message send 91xxxxxxxxxx "Your message"
```

The replies will be displayed on your Raspberry Pi.
Applications

You can use WhatsApp on Raspberry Pi as an efficient but cheap communication media for sending alerts or activation messages in your raspberry-pi projects related to automation, monitoring or surveillance. Thus the applications for WhatsApp on Raspberry Pi are endless.

