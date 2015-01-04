SSH-Honeypot
==============

This tool is a simple SSH server in Python which logs all username/password combinations into a logfile.

#Requirements

* ssh-keygen
* python (2.7 or 3.0)
* python-setuptools
* (iptables)

#Installation

* You need to install the ```paramiko``` module. (e.g. ```sudo easy_install paramiko```)
* Clone the repository. ```git clone https://github.com/internetwache/SSH-Honeypot.git``` and switch into the directory ```cd SSH-Honeypot```
* Generate the keypair: ```ssh-keygen -t rsa -f server.key```

#Configuration

* To change the ssh port, edit ```SSH_PORT = 2222```
* To change the logfile name, edit ```LOGFILE = 'logins.txt'```

You should use iptables to redirect the SSH traffic from port 22 to 2222 instead of running the script with root privileges. 

```/sbin/iptables -A PREROUTING -t nat -p tcp --dport 22 -j REDIRECT --to-port 2222```

#License

This piece of software is lincensed under MIT. See LICENSE.md for more information