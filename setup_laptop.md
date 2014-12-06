#<center> Set up your laptop in Ubuntu
<center>*Arkin Dec 5 2014*

---------------------------------------------

## install Ubuntu

    sudo apt-get update
    sudo apt-get upgrade
---------------------------------------------    
## input method    
language support    
text entry setting  
preference setting  

----------------------------------------------
## set up the bash
[REF](https://help.ubuntu.com/community/CustomizingBashPrompt)  

    gedit ~/.bashrc   
    
>uncomment the line     
from  
    #force_color_prompt=yes     
to  
    force_color_prompt=yes
    
----------------------------------------------

## install logitech unifying
    sudo add-apt-repository ppa:daniel.pavel/solaar
    sudo apt-get update
    sudo apt-get install solaar

----------------------------------------------

## install　ROS
[ROS](www.ros.org)

----------------------------------------------

## install vim 
    sudo apt-get install vim      
*set up the vim*   

* create (or edit) the .vimrc file:   
    vim ~/.vimrc    
* paste the configuration below into the file.   

        set tabstop=4       " The width of a TAB is set to 4.
                            " Still it is a \t. It is just that
                            " Vim will interpret it to be having
                            " a width of 4.
        set shiftwidth=4    " Indents will have a width of 4
        set softtabstop=4   " Sets the number of columns for a TAB
        set expandtab       " Expand TABs to spaces
        " set nu
        syntax on
        set autoindent      " auto indent
    
* restart vim

----------------------------------------------

## install sublime-text-3 
    sudo add-apt-repository ppa:webupd8team/sublime-text-3
    sudo apt-get update
    sudo apt-get install sublime-text-installer

----------------------------------------------

## install others    
    sudo apt-get install tex-live
    sudo apt-get install tex-maker
    sudo apt-get install skype
    sudo apt-get install dropbox
    sudo apt-get install everpad
    sudo apt-get install Gparted
    sudo apt-get install partitionmanager
    sudo apt-get install retext

*retext is a editor based on Markdown* 
[how to use retex](https://github.com/LearnShare/Learning-Markdown)

----------------------------------------------

## follow Ellen's note

### install packages

    sudo apt-get install swig
    sudo apt-get install openjdk-7-jdk
    sudo apt-get install flex
    sudo apt-get install libboost-all-dev libboost-dev
    sudo apt-get install libgsl0-dev
    sudo apt-get install libeigen3-dev 
    sudo apt-get install libatlas-dev
    sudo apt-get install libatlas-base-dev
    sudo apt-get install libatlas3gf-base

<big>install Armadillo</big>

…by downloading it from the website, not via apt-get, and follow the instructions in the readme. Make sure to do all the –devs and parallel stuff it mentions.

http://arma.sourceforge.net/download.html

Update: Do NOT install OpenBLAS. 
OpenBLAS has a multi-threading affinity which results in the creation of threads when solving certain classes of problems. Unfortunately, this results in high overhead as the system rapidly creates, clones, and yields numerous threads. This issue is linux specific.

<big>install yaml-cpp package</big>

Again, download “yaml-cpp_0.5.1.tar.gz” from their website and install using the readme.

https://code.google.com/p/yaml-cpp/ 

###install bison
Go to [gnu project archives](http://ftp.gnu.org/gnu/bison)  
download the “bison-2.5.tar.gz”

    sudo apt-get install m4

go into bison-2.5/lib, open stdio.in.h, and find the following lines:

    /* It is very rare that the developer ever has full control of
    stdin, so any use of gets warrants an unconditional warning.
    Assume it is always declared, since it is required by C89.  */
    #if defined gets
    #undef gets
    _GL_WARN_ON_USE (gets, "gets is a security hole - use fgets 
    instead");
    #endif

Comment out or delete the above lines. Finally,

    ./configure
    make
    sudo make install

###install IPC
Download IPC & unpack it.
[IPC](http://www.cs.cmu.edu/~./IPC/)

Change IPC flag

set -fPIC flag as described on [ipc_bridge doc](https://github.com/nmichael/ipc_bridge)

Find the ipc-3.9.1/etc/GNUmakefile.defs file.

Go to line 371.

Change:

    $(CFLAGSM_$(DBMALLOC)) $(CFLAGS_EXT)

to be

    $(CFLAGSM_$(DBMALLOC)) $(CFLAGS_EXT) -fPIC

Now, Install IPC

    sudo make

(There are some errors displayed earlier in the make, but these do not appear to break the components we need)

manually copy some files to new folders

ipc3.9.*/{bin/Linux*, lib/Linux*, include} to /opt/ipc/{bin,lib,include} 

NOTE:   
Do NOT add "LINUX*" directory in the destination directory when copying files from ipc     

    ipc3.9.*/{bin/Linux*, lib/Linux*, include} 
    
to  

    /opt/ipc/{bin,lib,include} 

###install Matlab

----------------------------------------------

## install mv-camera-driver
reboot
test via wxPropView
install ROS-camera-driver
copy camera calibration file
test image_view
test stereo_view

----------------------------------------------

## download sandbox
git clone URL
./update --devel



----------------------------------------------

## install gperftools
[google performance tools]()

----------------------------------------------



## setup printer in FRC.RI.CMU

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

----------------------------------------------

## install system monitor
    sudo add-apt-repository ppa:fossfreedom/indicator-sysmonitor
    sudo apt-get update
    sudo apt-get install indicator-sysmonitor
    sudo apt-get remove indicator-sysmonitor # to remove indicator sysmonitor
    sudo apt-get install indicator-multiload
 
 ----------------------------------------------
    
## use GitHub
### ssh key

    ls -al ~/.ssh
    ssh-keygen -t rsa -C "your_email@example.com"    
*start the ssh-agent in the background*
    eval "$(ssh-agent -s)"
    ssh-add ~/.ssh/id_rsa

### command set
    git add file-name
    git commit -m "commit message"
    git push
    
    git rm file-name
    git commit -m "remove a file"
    git push
    
    modify file-1
    git commit file-1 -m "modify this file"
    git push
    
    git add file-names
    git commit -a -m "creat"
    git push
 
 --------------------------------------------------------
    
## Wiki of px4
[px4 quick start](https://pixhawk.org/dev/px4_quickstart)
### NuttShell (NSH) via Seiral using the kermit:
[Ref](https://pixhawk.org/users/serial_connection)

    sudo apt-get install ckermit
    *Set your default settings to the correct settings for px4:*  
    echo "SET LINE /dev/ttyUSB0
    SET SPEED 57600
    SET CARRIER-WATCH OFF
    SET FLOW-CONTROL NONE" > ~/.kermrc
    
    ~/.kermrc
    ls /dev/ttyUSB*     
    sudo kermit
    connect
    enter

*command:*  

    ls 
    free 
    cd

*quit:* 
 
    Ctrl+\  
    C   
    quit

### build and flash the firmware 

    cd ~/src
    git clone https://github.com/PX4/Firmware
    cd Firmware
    *GitLab special start*
    git clone git@nmichael.frc.ri.cmu.edu:px4/px4_patches.git
    git checkout -b cmu_develop `cat px4_patches/px4_master_hash`
    git apply --ignore-space-change --ignore-whitespace px4_patches/px4_master_to_cmu_develop_version.diff
    rm -fr src/modules/cmu_rc_command src/modules/cmu_pwm_command src/modules/cmu_attitude_estimator_so3 src/modules/cmu_voltage_monitor
    git submodule add git@nmichael.frc.ri.cmu.edu:px4/cmu_rc_command.git src/modules/cmu_rc_command
    git submodule add git@nmichael.frc.ri.cmu.edu:px4/cmu_voltage_monitor.git src/modules/cmu_voltage_monitor
    git submodule add git@nmichael.frc.ri.cmu.edu:px4/cmu_attitude_estimator_so3.git src/modules/cmu_attitude_estimator_so3
    git clone https://github.com/PX4/NuttX
    *GitLab special end*
    
    git submodule init
    git submodule update
    
    *GitLab special*
    vim makefiles/config_px4fmu-v1_default.mk
    
    change line 129:
    From:
    MODULES                += modules/cmu_pwm_command
    To:
    #MODULES                += modules/cmu_pwm_command
    
    cd ~/src/Firmware
    make distclean
    make archives
    make
    sudo usermod -a -G dialout $USER
    Log out and log in in linux for changes to take effect. (Very Important!)
    make upload px4fmu-v1_default



The result should be:

working in [...]/Firmware/Images    
Attempting to flash PX4FMU board via USB    
Loaded firmware for 5,0, waiting for the bootloader...  

When you see “waiting for the bootloader” press the “reset” button on the side of the PX4FMU. If the board is now connected & reset, the new firmware will be flashed.  

Found board 5,0 on /dev/tty...  
erase...    
program...  
verify...   
done, rebooting.    

### Troubleshooting 
####Board not found (Affects mostly Ubuntu 12.10 users) 
In case the board is not found, make sure you remove the modem-manager by:  
    sudo apt-get remove modemmanager    

####Permission Denied
If you have no permissions for /dev/ttyACM0 , make sure the user is in group dialout (as described above).      

    sudo usermod -a -G dialout $USER     
         
Log out and log in in linux for changes to take effect. (Very Important!)

####To find out the device name (if not /dev/ttyACM0), do a
    ls /dev/tty*    
when the bootloader is loading (first 5 seconds after reset).

### install Qground control 


[Qgroundcontrol](http://qgroundcontrol.org/dev/build_source)

[github](https://github.com/mavlink/qgroundcontrol.git)

[installation instruction](https://github.com/mavlink/qgroundcontrol/blob/master/README.md)

### px4 serial port mapping
ttyS (definition in the px4/microSD/etc/rc.txt) 
HW (defined in the px4 hardware user manual)    

    ttyS0 <==> HW-UART1     
    ttyS1 <==> HW-UART2     
    ttyS2 <==> HW-UART5     
    ttyS3 <==> HW-UART6     

    UART_1 --- FTDI  
    pin3 --- black--ground
    pin7 --- yellow
    pin8 --- orange


### odroid cmu_mavlink 
    git clone cmu_mavlink
    ./update --devel
####trouble shooting 
[Ref](https://github.com/gitlabhq/gitlabhq/issues/4272#issuecomment-22074932)   
odroid sandbox update failed like this: 
[ 12%] Performing download step (git clone) for 'mavlink'   
Cloning into 'mavlink'...   
fatal: unable to access 'https://github.com/mavlink/mavlink.git/':   server certificate verification failed. CAfile: /etc/ssl/certs/ca-certificates.crt CRLfile: none   
solution:   
    git config --global http.sslverify false    
    


after the update:   
    catkin_make the dry;
    catkin_make the wet;

modify: vim cmu_mavlink/cmu_mavlink_only.launch     
    baudrate:230400     
    serialport:/dev/ttyUSB0

    roslaunch cmu_mavlink cmu_mavlink_only.launch
    rostopic list
    rostopic hz /mavlink/att
    rostopic echo /mavlink/att
---------------------------------------------------------------------
##Feedback control using Simulation via Matlab and IPC 

### download cmu_quad_matlab to sandbox
    git clone
    ./update  --devel
    
### compile the packages
solve the problem in vicon-mocap        
goto: cmu-quad-matlab/dry/src/vicon_mocap/libvicon_driver/

Change the following line:

Line 24:

from:   

    set(USE_OLD_YAML_CPP_API TRUE CACHE BOOL "Use the old YAML-CPP API")

to: 

    set(USE_OLD_YAML_CPP_API FALSE CACHE BOOL "Use the old YAML-CPP API")

catkin_make wet, it depends on some packages in dry, so before the compile we should source dry directory. (solution to problem "can't find mavlink".)
 
### . workon
mehtod_1: manually source:
    firstly souce dry, then source wet
    source ${TOP_DIR}/dry/install_isolated/setup.bash
    source ${TOP_DIR}/wet/devel/setup.bash
method_2: use workon
add --extend to the second source line to make sure it works correctly.
there is a space between . and workon in command line

### let ROS talk to IPC-bridge
    /opt/ipc/bin/central –u
### run Matlab.simple_io_test.m
    cd /cmu_quad_matlab/wet/src/matlab_quadrotor_example/matlab
*NOTE*   
*Be careful when trying to print out some information, which can greatly slow the processing speed.*
### run launch file
    cd cmu_quad_matlab/wet/src/matlab_quadrotor_example/launch
    roslaunch matlab_quadrotor_example simulation_test.launch
    rostopic list
    rostopic hz topic-name
    rostopic echo topic-name
###trouble shooting 
rostopic echo  /test/pd_cmd

ERROR: Cannot load message class for [quadrotor_msgs/PDCommand]. Are your messages built? 
      
solution: source the directory using . workon in current terminal

----------------------------------------------------






    
    
