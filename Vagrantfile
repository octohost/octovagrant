# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "octohost"
  config.vm.box_url = "https://dl.dropboxusercontent.com/u/695019/vagrant/octovagrant.box"
  config.vm.box_download_checksum_type = "sha1"
  config.vm.box_download_checksum = "e15256bafaa7cc295f08a3519e94988997900d08"
  config.vm.network :private_network, ip: "192.168.62.86"
end
