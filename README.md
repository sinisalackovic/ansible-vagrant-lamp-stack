# Ansible Vagrant LAMP Stack
# Requirements

VirtualBox https://www.virtualbox.org/wiki/Downloads (based on your operating platform choose VM package) <br>
Vagrant https://www.vagrantup.com/downloads.html (based on your operating platform choose Vagrant)





# Note
1. If you have a problem with Kernel, check this article:

    https://apple.stackexchange.com/questions/300510/virtualbox-5-1-8-installation-didnt-install-kernel-extensions-how-do-i-fix-this

2. To setup a static address to your VM machine
 
    2.1 Check you Ethernet interface identity (in my case it's "enp0s3"): 
      
      	ifconfig -a | grep eth OR
      	ifconfig -a | grep enp

  	2.2 Edit an Ethernet interface file and replace a whole content: 
      
      	sudo gedit /etc/network/interfaces

      	auto lo enp0s3
      	iface lo inet loopback
      	iface enp0s3 inet static
          address 192.168.0.100
          netmask 255.255.255.0
          gateway 10.0.0.1

3. Generate a ssh key
    3.1 Generate the ssh key on the Host maschine (OSx):
        
        ssh-keygen -t rsa ('/Users/username/.ssh/id_rsa.pub')
        
    3.2 Install an openssh-client and openssh-server packages on your Virtual Machine to accept ssh connection:
        
        openssh-client AND openssh-server
    
    3.3 Copy the ssh generated key to your Virtual Machine: 
    
        ssh-copy-id root@192.168.0.100

    4.3 Check your ssh connection:
        
        ssh root@192.168.0.100
