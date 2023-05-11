### App deployment. 

It is possible to deploy our own apps to a virtual machine via the terminals. 

### Files mangement & Navigation

we need to ensure that we have the correct files downloaded. In our case there are 2 files we need to download and extract. They are names: ```app``` and ```environment```

Due to security I won't share the files themselves. they need to be extracted and place din the correct file. 
The same file as our app deployment. in my case they can be seen as: 
![Alt text](files.png)

before we move onto the nect step make sure your in the correct file space in the terminal. Refer to my previous markdown files for more help but here is a quick rundown for navigation:

Use ```ls```: Lists files and directories in the current directory. 1.1. ls -a: shows all files, including hidden ones

Use ```cd```: Changes the current directory

additional help can be found:
``` https://www.digitalocean.com/community/tutorials/how-to-use-cd-pwd-and-ls-to-explore-the-file-system-on-a-linux-server ```

### Vagrant file changes

some adjustments need to be made our vagrant file. If there is not already one in our folder, we can copy in an exissting one or we can create a new one by using ```vagrant init```. We also need a shell file, we will use ```provisions.sh```  file in this file. we can create a new one or copy the old one. 

### Putting app file from local machine to Virtual machine

we need to put in aother line of code in the ```vagrantfile```, the line we will add is: ``` config.vm.synced_folder "app", "/home/vagrant/app" ```
Remember this line allows us to sync the files we added. 

Here is what the file should look like:
![Alt text](vagranpngj.png)

### Starting up vagrant

we need to use ```Vagrant up``` in the terminal in order to start the VirtualMachine. 

![Alt text](vm%20update.png)

### Using gitbash terminal 

on the gitbash terminal we need to arrive to the right location. Use the commands above (ls and cd) to navigate. 
Once arrived;  use ```vagrant ssh``` to access the VM through the gitbash terminal. Should look something like this:
![Alt text](gitbash.png)

Here i recomend checking the files, use ```ls``` and the file should hopefully be highlighted or it should appear. 
![Alt text](bash2.png)

now go into the ```app``` folder, this is so we can access it's contents.
use ```cd app```

Furthermore we can use ```pwd``` to check the contents. 

### Installing nodejs

The next steps are pretty straight forward and can take some time to complete depending on your system capabilities. we need to run ``` sudo apt-get install nodejs ```. This installs nodejs. It should result in something similar to: 
![Alt text](aaaf.png)
followed by alot of code.

we can check the version via ```nodejs --version```

### installing python softwares

Next we need to install another package using the following command: ```  sudo apt-get install python-software-properties ```

hopefully resulting in something similar to: 
![Alt text](ssss.png)
if a confirmation is required, confirm it. 

### Retrieving the software

Next we need to use a URL in order to retrieve the package. the URL is: ``` https://deb.nodesource.com/setup_6.x ```

combine this with the following line of code:
``` curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash - ```

resulting in:
![Alt text](fsd.png)

### Install 

use: ``` sudo apt-get install -y nodejs ``` and confirm it. resulting in: 
![Alt text](aaaaafffff.png)

use: ``` sudo apt-get install nodejs -y ```
there is no need to confirm this one as we used ```-y```. Note: this can be used in many places not just here. 

use ``` sudo npm install pm2 -g ```
resulting in: 
![Alt text](sdfsdfdsf.png)

in order to verify it has worked we can enter the IP address followed by the port into a browswer, ```192.168.10.100:3000```
Resulting in:
![Alt text](verify.png)


