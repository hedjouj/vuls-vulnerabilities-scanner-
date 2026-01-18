
# Vuls - open source vulnerabilities scanner

Today I'm goona install and use Vuls - to scan my local systems to check If I got any vulnerabilities. I used an Linux magazine to make this project (Optimum linux edition 2)



## Installation

On ubuntu - First we update our system


```bash
  sudo apt-get update && sudo apt-get upgrade -y
```

## Install depencies

```bash
sudo apt-get install debian-goodies reboot-notifier-y

```

## Download the installation script


```bash
wget httpps://raw.githubusercontent.com/vulsio/vulsctl/master/install-host/install.sh


```

## Make the script executable


```bash
chmod u+x install.sh


```

## Launch the installation


```bash
sudo ./install.sh
```
## Check the install


```bash
vuls help
```

## Now launch the scan


```bash
sudo vuls scan localhost
```
If you get this error:

"sudo vuls scan localhost [Jan 17 17:10:37] INFO [localhost] vuls-v0.37.0-build-20260117_170153_266f9db [Jan 17 17:10:37] ERROR [localhost] Error loading /home/hedjouj/config.toml If you update Vuls and get this error, there may be incompatible changes in config.toml Please check config.toml template : https://vuls.io/docs/en/config.toml.html open /home/hedjouj/config.toml: no such file or directory"

It means your configuration file is missing

## Then, create config.toml file

```bash
nano config.tml
```
And write this in the text file:
[servers]

[servers.localhost] host = "localhost" port = "local"

## Launch again the scan

```bash
sudo vuls scan localhost
```
And watch the results in the interactiv ui

```bash
sudo vuls tui
```


## Screenshots

![App Screenshot](/screen_scan_result.png)

