# Pi Digital Signage Control

Step by step to control Digital Signage with Raspberry Pi 3 running on Stretch

—COMMANDS ON SSH
#enabling and starting SSH

sudo systemctl enable ssh
sudo systemctl start ssh

#install git

sudo apt-get install git-core -y

#create dev folder with permission

sudo mkdir -m777 dev && cd dev

#install Python PIP

sudo apt-get install python3-pip -y && sudo apt-get install python-pip -y

#increase GPU mem and disable GL driver

sudo raspi-config

##OR##

sudo nano /boot/config.txt

gpu_mem=192
dtoverlay=vc4-kms-v3d


#install beamer dependencies

sudo apt-get install libevent-2.0-5 libavformat57 libpng12-0 libfreetype6 libavresample3 -y

#get info-beamer

cd dev && wget https://info-beamer.com/jump/download/player/info-beamer-pi-0.9.9-beta.132ee8-stretch.tar.gz

#unzip

tar xf info-beamer-pi-0.9.9-beta.132ee8-stretch.tar.gz

#run info-beamer

INFOBEAMER_BLANK_MODE=layer ./info-beamer samples/
