# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  # This box has guest additions:
  # https://github.com/holms/vagrant-centos7-box/releases/download/7.1.1503.001/CentOS-7.1.1503-x86_64-netboot.box
  config.vm.box = "centos7"

  # Application
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.vm.network "forwarded_port", guest: 8080, host: 18080

  # Postgres
  config.vm.network "forwarded_port", guest: 5432, host: 15432

  # Node Debugger
  config.vm.network "forwarded_port", guest: 5858, host: 15858

  # Sync apps folder as your workspace
  config.vm.synced_folder "apps/", "/vagrant"

  config.vm.define "devenv" do |site|
      site.vm.provision :ansible do |ansible|
          ansible.playbook = "dev.playbook.yml"
      end
  end
end
