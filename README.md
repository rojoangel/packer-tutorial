How-to packer command-line
==========================
Validate template
-----------------
    packer validate example.json

Build from template
-------------------
    packer build example.json

Requirements to build a vagrant box
===================================
Install virtual box
-------------------
Update sources by editing sources.list 
    sudo vi /etc/apt/sources.list
and adding
    deb http://download.virtualbox.org/virtualbox/debian squeeze non-free

Execute the following commands
    wget -q http://download.virtualbox.org/virtualbox/debian/oracle_vbox.asc -O- | sudo apt-key add -
    sudo apt-get update
    sudo apt-get install virtualbox-4.3

Install vagrant
---------------
    sudo apt-get install vagrant

