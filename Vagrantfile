# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.ssh.insert_key = false
  config.vm.provider :virtualbox do |provider, override|
    provider.name = "centos6.7"
    provider.memory = 1024
    provider.cpus = 1
  end

  config.vm.box = "bento/centos-6.7"
  config.vm.hostname = "vagrant001"

  # Port設定
  config.vm.network 'forwarded_port', guest: 80, host: 8080
  config.vm.network 'forwarded_port', guest: 443, host: 4443

  # IP設定
  config.vm.network :private_network, ip: "192.168.34.23"
  # localの共有フォルダのマウント
  config.vm.synced_folder ".", "/vagrant", mount_options: ["dmode=777", "fmode=666"]
end
