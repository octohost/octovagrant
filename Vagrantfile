# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "octohost"
  config.vm.box_url = "https://dl.dropboxusercontent.com/u/695019/vagrant/octovagrant-0.7.6.box"
  config.vm.box_download_checksum_type = "sha1"
  config.vm.box_download_checksum = "10ab0010e6418cfdf76f03a381378f4e0d3ee47b"
  config.vm.network :private_network, ip: "192.168.62.86"
end
