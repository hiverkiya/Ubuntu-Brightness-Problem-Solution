# Ubuntu-Brightness-Fix 
The brightness configuration file for Ubuntu and it's derivatives like Linux-Mint ,Kubuntu etc.
# Method-1
 
 You just have to place the configuration file in "/usr/share/X11/xorg.conf.d" directory.
  
  For this, write commands written below one by one :-
  
  * cd /usr/share/X11/xorg.conf.d
  
  * wget https://github.com/Verkiya/Ubuntu-Brightness-Fix/blob/master/20-intel.conf
  
  After that just logout/restart to check  whether brightness function is fixed or not.
 
# Method-2
 
 Commands are under quotes.
 
 Follow below mentioned steps:-
 
* Check for video/graphics card "ls /sys/class/backlight" (Proceed if intel_backlight)

* Make the configuration file "sudo touch /usr/share/X11/xorg.conf.d/20-intel.conf"

* Open configuration file any text editor of your choice gedit/vim/anyone either via GUI or CUI , in case of terminal write " sudo gedit /usr/share/X11/xorg.cong.d/20-intel.conf"

* Add the following lines to it :-

     
      Section "Device"
    
            Identifier  "card0"
            
            Driver      "intel"
            
            Option      "Backlight"  "intel_backlight"
            
            BusID       "PCI:0:2:0"
            
      EndSection
      
    
 
 * Save it , either logout or restart.Brightness control would be working by now.
 
 [Source](https://itsfoss.com/fix-brightness-ubuntu-1310/)

