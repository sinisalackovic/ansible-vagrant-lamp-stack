# Ansible Vagrant LAMP Stack
# Requirements

VirtualBox https://www.virtualbox.org/wiki/Downloads (based on your operating platform choose VM package) <br>
Vagrant https://www.vagrantup.com/downloads.html (based on your operating platform choose Vagrant)





# Note
1. If you have a problem with Kernel, check this article:

https://apple.stackexchange.com/questions/300510/virtualbox-5-1-8-installation-didnt-install-kernel-extensions-how-do-i-fix-thi

2. To setup a static address to your VM machine
  2.1 Check you Ethernet interface identity (in my case it's "enp0s3"): 
      
      ifconfig -a | grep eth OR 
      ifconfig -a | grep enp

  2.2 Edit Ethernet interface file and replace a whole content: 
      
      sudo gedit /etc/network/interfaces

      auto lo enp0s3
      iface lo inet loopback
      iface enp0s3 inet static
          address 10.0.0.100
          netmask 255.255.255.0
          gateway 10.0.0.1
