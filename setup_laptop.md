#<center> Set up your laptop in Ubuntu

<center>*Arkin Dec 5 2014*

[google](www.google.com)    
[how to use retex](https://github.com/LearnShare/Learning-Markdown)

* item 1
* item 2

1.item 3   
========== 
2.item 4
-----

##2
###3
####4
#####5


<u>what</u>

-----------------
-----------------

--------------------

##1. install Ubuntu

    sudo apt-get update
    sudo apt-get upgrade
##2. basic setting
input method    
language support    
ibus-setup  
 
##3. set up the bash
[REF](https://help.ubuntu.com/community/CustomizingBashPrompt)  
    gedit ~/.bashrc   
uncomment the line from    
    #force_color_prompt=yes 
to  
    force_color_prompt=yes

##4. install logitech unifying
    sudo add-apt-repository ppa:daniel.pavel/solaar
    sudo apt-get update
    sudo apt-get install solaar

##5. install　ROS
[ROS](www.ros.org)

##6. install vim install mv-camera-driver
reboot
test via wxPropView
install ROS-camera-driver
copy camera calibration file
test image_view
test stereo_view

##7. download sandbox
git clone URL
./update --devel


##8. follow Ellen's note
install IPC
install Matlab


##9. install gperftools
[google performance tools]()

##10. install sublime-text-3 
    sudo add-apt-repository ppa:webupd8team/sublime-text-3
    sudo apt-get update
    sudo apt-get install sublime-text-installer

##11. install others    
    sudo apt-get install tex-live
    sudo apt-get install tex-maker
    sudo apt-get install skype
    sudo apt-get install dropbox
    sudo apt-get install everpad
    sudo apt-get install Gparted
    sudo apt-get install partitionmanager
    sudo apt-get install retext
*retext is a editor based on Markdown*

##12. setup printer in FRC.RI.CMU

If you have an SCS account there are several ways to print:

The prefered method is here.    
In linux (Ubuntu):  
Go to System -> Administration -> Printing      
Click 'Add' 
Expand 'Network Printer'    
Select 'LPD/LPR Host or Printer'       
change the Host and Queue fields. Queue is the name of the printer.
   
####Printer IP	FQDN	Model	Location 	Host 
    
    boulder	
    128.2.177.195	
    boulder.prt.cs.cmu.edu	
    HP Color Laserjet 5550N	
    NSH 1100 (near FRC mailboxes)	
    cyan.srv.cs.cmu.edu
    
    lightning	
    128.2.177.194	
    lightning.prt.cs.cmu.edu	
    HP Laserjet 9000N	
    NSH 1200 (near e-lab)	
    cyan.srv.cs.cmu.edu
    
    mulch	
    128.2.177.211	
    mulch.prt.cs.cmu.edu	HP Laserjet 4350n	
    NSH 2200 (near FRC grad student offices and water cooler)	
    cyan.srv.cs.cmu.edu
    
    prismCOLOR	
    128.2.177.208	
    prismcolor.prt.cs.cmu.edu	
    HP Color Laserjet 5550DN	
    NSH 1509 (near NSH 1st floor copy room and RoboLounge)
    cyan.srv.cs.cmu.edu

================================
##13. install system monitor
    sudo add-apt-repository ppa:fossfreedom/indicator-sysmonitor
    sudo apt-get update
    sudo apt-get install indicator-sysmonitor
    sudo apt-get remove indicator-sysmonitor # to remove indicator sysmonitor
    sudo apt-get install indicator-multiload
