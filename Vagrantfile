# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "kensykora/windows_2012_r2_standard"
  config.vm.network 'private_network', ip: '192.168.50.4'
  config.vm.network "forwarded_port" , guest: 3389, host: 53389

  config.vm.provision 'chef_zero' do |chef|
    chef.roles_path = 'roles'
    chef.add_role 'windowsnode'
  end
end
