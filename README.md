# vuls-vulnerabilities-scanner-
Installing and testing Vuls, an open source vulnerability scanner

Installation

On ubuntu - First we update our system

sudo apt-get update && sudo apt-get upgrade -y

Install depencies
 sudo apt-get install debian-goodies reboot-notifier-y

 Download the installation script
 wget httpps://raw.githubusercontent.com/vulsio/vulsctl/master/install-host/install.sh

 Make the script executable
 chmod u+x install.sh

 Launch the installation 
 sudo ./install.sh

 Check the install
 vuls help

Now launch the scan with
sudo vuls scan localhost

 If you get this error: 
 
"sudo vuls scan localhost
[Jan 17 17:10:37]  INFO [localhost] vuls-v0.37.0-build-20260117_170153_266f9db
[Jan 17 17:10:37] ERROR [localhost] Error loading /home/hedjouj/config.toml
If you update Vuls and get this error, there may be incompatible changes in config.toml
Please check config.toml template : https://vuls.io/docs/en/config.toml.html
open /home/hedjouj/config.toml: no such file or directory" 

It means your configuration file is missing

Then, create config.toml file
nano config.tml 
And write this in the text file: 
[servers]

[servers.localhost]
host = "localhost"
port = "local"

Now launch again the scan
sudo vuls scan localhost

And watch the results in the interactiv ui

[SCREENSHOT] 

Now let's analyze a distant server with RHEL 9 (Red Hate Entreprise Linux 9) 


