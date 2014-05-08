# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.require_version ">= 1.5.0"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "darron/octohost"
  config.vm.network :private_network, ip: "192.168.62.86"
  config.vm.post_up_message = "############ Setup your keys in order to use your octohost ############\n\nvagrant ssh -c \"curl -L https://github.com/{your-username}.keys >> /home/vagrant/.ssh/authorized_keys\"\n\nThen:\n\ncat ~/.ssh/{your-key.pub} | ssh vagrant@server.octodev.io \"sudo gitreceive upload-key {your-name}\""
end
