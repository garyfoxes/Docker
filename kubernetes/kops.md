brew update && brew install kops (Install)

brew doctor

brew install python (going to use python-pip for using aws command line)
sudo easy_install pip
sudo -H pip install --ignore-installed awscli (Install command line for aws)

If there are permission issues run:

sudo mkdir /usr/local/Frameworks
sudo chown $(whoami):admin /usr/local/Frameworks
