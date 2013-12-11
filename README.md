docker/anaconda
===============

### Setup
```bash
sudo apt-get upgrade
wget http://09c8d0b2229f813c1b93-c95ac804525aac4b6dba79b00b39d1d3.r79.cf1.rackcdn.com/Anaconda-1.8.0-Linux-x86_64.sh
bash Anaconda-1.8.0-Linux-x86_64.sh 
openssl req -x509 -nodes -days 365 -newkey rsa:1024 -keyout mycert.pem -out mycert.pem
. .bashrc 
ipython profile create nbserver
cd 
# Move this local file to 
mv ipython_notebook_config.py ~/.ipython/profile_nbserver/ipython_notebook_config.py 
sudo -s
```

### Run
```bash
# Source updated rc
sh ~/.bashrc 
iptables -I INPUT -p tcp --dport 80 -j ACCEPT
iptables -I INPUT -p tcp --dport 443 -j ACCEPT
ipython notebook --profile=nbserver
```
