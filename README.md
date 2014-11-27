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

Building the vagrant box
------------------------
    packer build vagrant-example.json
It will output the following message when completed
    ==> Builds finished. The artifacts of successful builds are:
    --> virtualbox-iso: 'virtualbox' provider box: build/centos-6.5-x86_64.box
and the created vagrant box made available at the ./build directory
    cd build
    vagrant init
    vagrant box add build/centos-6.5-x86_64 ./centos-6.5-x86_64.box
Configure the box as the base for our project by changing the `Vagrant file`contents to the following
    config.vm.box = "build/centos-6.5-x86_64"
Start and connect to the box by running
    vagrant up
    vagrant ssh
