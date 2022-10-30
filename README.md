# Ubuntu Brightness Fix 

If the brightness buttons are not working or brightness isn't varying, then a brightness configuration file is provided; either download or create it with the methods mentioned below. Make sure you're a root user in this process.

# Method 1
 
 You must place the configuration file in the "/usr/share/X11/xorg.conf.d" directory. Open Terminal with Superuser privileges
 
 And execute the commands given below.
 
  * cd /usr/share/X11/xorg.conf.d
  
  * wget https://raw.githubusercontent.com/hiverkiya/Ubuntu-Brightness-Problem-Solution/master/20-intel.conf
  
  After that, just log out/restart to check whether the brightness function is fixed or not.
 
# Method 2
 
 Commands are under quotes.
 
 Follow the below-mentioned steps:-
 
* Check for video/graphics card "ls /sys/class/backlight" (Proceed if intel_backlight).

* Make the configuration file "sudo touch /usr/share/X11/xorg.conf.d/20-intel.conf"(Enter the root password, if not root).

* Open the configuration file with any text editor of your choice, gedit/vim/anyone, either via GUI or CUI.

* In case of the terminal, write " sudo gedit /usr/share/X11/xorg.conf.d/20-intel.conf" and in case of GUI, open text-editor and paste the section given below into it and save it with the name "20-intel.conf" in "/usr/share/X11/xorg.conf.d".

* Add the following lines to it:-

     
      Section "Device"
    
            Identifier  "card0"
            
            Driver      "intel"
            
            Option      "Backlight"  "intel_backlight"
            
            BusID       "PCI:0:2:0"
            
      EndSection
      
    
 
 * Save it; either log out or restart. Brightness control would be working by now.
 
 [Source](https://itsfoss.com/fix-brightness-ubuntu-1310/)

