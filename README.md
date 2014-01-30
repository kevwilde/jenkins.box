# Jenkins Vagrant Box

This vagrant box is provisioned with a default configured Jenkins instance for local testing and development. Feel free to expand!

# Requirements

* Berkshelf (http://www.berkshelf.com)
  Chef cookbook dependency management.
* vagrant-berkshelf plugin

# Getting Started

Simply run
    
    vagrant up

Berkshelf will automatically fetch all cookbook dependencies for us.

There's an example plugin configuration available as a reference if you wish to install more jenkins plugins. Check the Vagrantfile.
