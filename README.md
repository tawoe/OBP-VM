OpenBankProject-Virtual machine
=============

##About

This project is about

##Goals

##License

##Status

Works fine with http://files.vagrantup.com/precise64.box, some tweaking and testing in progress

##Setup

The project uses a Vagrant+Puppet to create/modify a virtualbox-machine, so obvious you'll need Vagrant and VirtualBox installed.  
 `apt-get install vagrant virtualbox`

The next step would be to clone this git-repo, if not allready done:  
 `git clone https://github.com/OpenBankProject/OBP-VM`

Now we import the basebox we'd like to use:  
 `vagrant box add obps http://files.vagrantup.com/precise64.box`  
 or  
 `vagrant box add obps http://files.vagrantup.com/precise32.box`  
 or sth else (not tested)

Finally we have to start the process by calling  
 `vagrant up`  
 (from the directory this README is in)

Now go and grab some coffee, it could take a while :)

After finishing the OpenBankProject-Server should run at localhost:7070/OBPS
(login is tesobe@tesobe.com / 123tesobe456)

##Further commands

Create new database  
`vagrant ssh -c "mongo localhost/OBP006 /vagrant/mktestdb.js"`

Restart jetty
`vagrant ssh -c "/etc/init.d/jetty restart"`

...

##Future

-Some GUI at localhost:7070/OBPS/conf?  
-Place an up to date-warfile in the obps-gitrepo so there's no need to compile on creation of a vm

##ToDo

more options for mkmongodb.js  
service { “jetty”: enable => true, ensure => running }  
 servicewatchdirbla

##Files

`/Vagrantfile`  
Vagrant config file; things like port forwarding and file access for the vm. In fact just  port forwarding and file access for the vm.

`/manifests/default.pp`  
THE puppet file; 

`/configs`  
other files needed like configs for jetty, maven and the mongodb-creation script

##Contact
