# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

# rsync fix: https://github.com/mitchellh/vagrant/issues/3230#issuecomment-62588180
ENV["VAGRANT_DETECTED_OS"] = ENV["VAGRANT_DETECTED_OS"].to_s + " cygwin"

Vagrant.configure(2) do |config|

  # rsync must be installed onto guest using install_rsync.cmd
  config.vm.box = "kensykora/windows_2012_r2_standard"
  config.vm.network 'private_network', ip: '192.168.50.4'

  # Note: guest path uses /cygdrive, even though cygwin is only installed on the host
  config.vm.synced_folder './my_share', '/cygdrive/c/my_share', type: 'rsync'

  config.vm.provision 'chef_zero' do |chef|
    chef.provisioning_path = 'C:/vagrant-chef'
    chef.file_backup_path = 'C:/chef/backup'
    chef.file_cache_path = 'C:/chef/cache'

    chef.roles_path = 'roles'
    chef.add_role 'windowsnode'
  end
end
