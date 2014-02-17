# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "octohost"
  config.vm.box_url = "https://dl.dropboxusercontent.com/u/695019/vagrant/octovagrant-0.8.box"
  #
  # Not sure why, but a Windows user reported a sha1 mismatch.
  # I've verified it a few times - and it's correct - not sure why it's failing.
  # So I've disabled it here for the moment.
  #
  # config.vm.box_download_checksum_type = "sha1"
  # config.vm.box_download_checksum = "3c21e2362dbf0a4cfd6b3b4d3a0843e58269a216"
  config.vm.network :private_network, ip: "192.168.62.86"
end
