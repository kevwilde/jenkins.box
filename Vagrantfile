# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  
  # -- Base

  config.vm.box = "debian7"
  config.vm.box_url = "https://www.dropbox.com/s/si19tbftilcuipz/debian-7.0-amd64.box"
  
  # -- Networking

  #config.ssh.forward_agent = true
  
  config.vm.network :forwarded_port, guest: 8080, host: 8080
  config.vm.network :forwarded_port, guest: 443, host: 4443
  config.vm.network "public_network", :bridge => 'eth0'

  # -- Shared Directories

  # -- Configuration Management

  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = "cookbooks"
    chef.add_recipe "apt"
    chef.add_recipe "git"
    chef.add_recipe "vim"
    chef.add_recipe "jenkins::server"
    chef.json = {
      "jenkins" => {
          "server" => {
              "plugins" =>
               [
                  "greenballs",
              ]
          }
      }
    }
  end

  config.berkshelf.enabled = true

end
