# ardupilot



Installing Ardupilot and MAVProxy


Clone ArduPilot



In home directory:



             cd ~
            
             
             sudo apt install git 
            
            
            git clone https://github.com/ArduPilot/ardupilot.git
            
            
            cd ardupilot
            
            
            git checkout Copter-3.6
            
            
            git submodule update --init --recursive




Install dependencies:
               
               
             
             
             sudo apt install python-matplotlib python-serial python-wxgtk3.0 python-wxtools python-lxml python-scipy python-opencv ccache gawk python-pip python-pexpect






Use pip (Python package installer) to install mavproxy:



               sudo pip install future pymavlink MAVProxy






Open ~/.bashrc for editing:

             

                gedit ~/.bashrc





Add these lines to end of ~/.bashrc (the file open in the text editor):



        
        
        export PATH=$PATH:$HOME/ardupilot/Tools/autotest
        
        
        
        export PATH=/usr/lib/ccache:$PATH





Save and close the text editor.


         
         
         Reload ~/.bashrc:


             
             . ~/.bashrc





Run SITL (Software In The Loop) once to set params:

 
             
             cd ~/ardupilot/ArduCopter

                   
              
              sim_vehicle.py -w
                   
                   
 
 
 Intalling QGroundControl
 
 

Installing QGroundControl for Ubuntu Linux 18.04 LTS :


Add current user accout to dialout group and remove modemmanager


               
               
               sudo usermod -a -G dialout $USER

               
               sudo apt-get remove modemmanager





Download QGroundControl.AppImage

          
          
          wget https://s3-us-west-2.amazonaws.com/qgroundcontrol/latest/QGroundControl.AppImage






Change permissions and run

               
               
               chmod +x ./QGroundControl.AppImage 

              
              
              ./QGroundControl.AppImage  (or double click)




Run SITL and connect with Q Ground
                
                
                
                cd ~/ardupilot/ArduCopter/
                
                
                
                
                sim_vehicle.py
