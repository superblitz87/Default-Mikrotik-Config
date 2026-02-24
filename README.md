##The issue

Netinstaller is a wonderful tool by Mikrotik (https://mikrotik.com/download/tools)

If one has a router from them that failed an update and is "Softlocked" (recoverable with a software reset), the Netinstall tool is invaulable to get it working again.
When possible always have "Keep Old Configuration" checked and leave "Apply Defualt Config" Unchecked.

There is a caviot, if one uses the feature "Apply Default Config", it will erase the Password that one has setup and will DEFAULT to a BLANK PASSWORD for the Admin account.
Along with this all network settings will be erased and internet access will be lost.

![unknown-admin-login-v0-8drxyeuw2rkg1](https://github.com/user-attachments/assets/20813f34-4444-4632-993b-5a7d16bfc2dd)


Also if one does not select "Apply Defualt Config" and "Keep Old Configuration", setting up IP address and Gateway manually; Internet access will be available, yet the password to the admin account to access the router is unkown to anyone.
Leaving the field blank will not allow access.
Using the Password on the bottom of the device will not allow access.
Trying any random password from the interent will not allow access.

https://youtu.be/QaeHRsrRWw0




##The Solution (more of a work around)

We were able to create a backup of a Config.rsc file that from a known good Mikrotik router.  
RSC files are the information that humans can read from the Mikrotik and these files can be opened in a Text editor.

Here are the steps (they are tedius, but they work):

1) Reset the router following the guide on MikroTiks website and their Youtube videos for NetInstall
2) if step 1 does not work, then perform the steps to get it in a configuration state (with netinstall open, hold the reset button while pluggin in power for 20 seconds or until you hear a beep)
3) Check "Apply Default Configuration"
4) Install the desired firmware (which is part of the instructions from the Mikrotik website/Youtube channel)
5) After the install, connect the PC to port 2 of the router and access the routers IP address or use Mikrotiks WinBox which will connect via the Mac of the Router. (https://mikrotik.com/download/winbox)
6) Login (username should be admin; password will not need a password)
7) Create a new password for your router
8) Access "New Terminal" inside the router
9) Access the Config file on this page
⚠️ On the 2nd Line of the config, "admin-mac", the MAC address should be edited to match what is on your Router as well as the Mac that is shown in WinBox for your device or the Mac that is shown in Netinstall for it.⚠️
10) Copy the lines into New Terminal to have them added to the router. (We suggest doing it one line at a time, just so if an error were to occur it would be easy to figure out where it came from)
