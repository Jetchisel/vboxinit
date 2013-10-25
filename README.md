sysV-vboxinit
=============



  vboxinit: auto start sessions when booting and save
   sessions when host is stopped

  Based on vboxtool. Rewritten/modified  for OpenSuSE by jetchisel.
  
 
 copy this script to /etc/init.d
 
 ----
 uncomment "var $startStopConfig = true;" in phpvirtualbox's php.ini
 
 ----
 Configure vms in phpvirtualbox's graphical menu for statupmode = automatic
 
 Settings --> General --> Basic --> "StartupMode --> Automatic"

----  
 Set permissions
 
 chmod u+rx /etc/init.d/vboxinit
 
---- 
 Enable at boot time      
 
 chkconfig vboxinit on
  
----

 For testing the script as root run:  

 /etc/init.d/vboxinit {start|stop|restart|status}

---- 
 NOTE:
      the script runs the vms as a normal user that is defined in /etc/default/virtualbox 
      and belongs to the vboxusers group so you will not worry about running the script as
      root.


vboxinit comes from the phpvirtualbox project which works for sysV init.This is the
modified/rewritten version for openSuSE using systemd.Kudos to Ian Moore the autor of phpvirtualbox
