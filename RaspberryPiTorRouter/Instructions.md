##Description
Turn a Raspberry Pi into a wireless AP that routes all your traffic through the Tor.
Details. 

As of Jessie, Raspbian uses systemd, which makes many of these settings easier to do by hand than messing with IPtables. Since systemd is the new standard that most Linux distros are using, the scripts will have to be rewriten to take advantage of this fact. However, the current instructions still work just fine.

##Instructions  

The preferred OS is Raspbian.  

1. From a terminal or command line, run 'sudo apt-get update' and then 'sudo apt-get upgrade' to update all the software to the latest version. We need to do this before installing the Hot Spot software since it needs to be a specific version, and an update would break its ability to work correctly.  
2. Make sure your WiFi device is NOT plugged into your Pi. We need to make pifi.sh executable so we can run it. Do so by typing the following:  
```
chmod +x pifi.sh
```
Now type the following to run the script and setup your new WiFi Access Point:  
```
sudo ./pifi.sh
```
Follow all the instructions on the screen. The script will reboot your Pi when it is finished.  
3. Log back in and safely shut down your Pi. Insert your WiFi dongle and power everything back on. You should now see an extra WiFi source in your home! At the moment, it is just a normal WiFi source, just like your wireless router. The SSID is whatever you named it in the previous step, and the password will be whatever you specified. If you want to SSH into your Pi, you can do so over the Ethernet IP address that your primary router assigned, or over the new WiFi connection if you connect through it. That address would be 192.168.42.1 over WiFi.  
4. To add the Tor routing capability, we will need the Tor script.  
Just like before, we need to make it executable:
```
chmod +x tor.sh
```
5. Run the script by typing:  
```
sudo ./tor.sh
```
Follow any prompts and wait for your Pi to reboot.
6. When you connect to this WiFi source, all your web traffic should be routed through the Tor. You can verify this by going to https://check.torproject.org/  


