octovagrant
===========

Some helpful files when using octohost with Vagrant.

    # Install Docker Mac binary
    brew tap homebrew/binary
    brew install docker
    brew install direnv # More info here: https://github.com/zimbatm/direnv


NOTE: If you are using Vagrant 1.6+, the Vagrantfile will work without modification. If you're using < 1.6 then you can find the necessary URL at [Vagrant Cloud](https://vagrantcloud.com/darron/octohost/versions).

There are two ways to proceed from here:

### Use the already built Vagrant box.

    vagrant up # The box will be downloaded, verified and installed.
    vagrant ssh -c "curl -L https://github.com/{your-username}.keys >> /home/vagrant/.ssh/authorized_keys"
    cat ~/.ssh/{your-key.pub} | ssh vagrant@server.octodev.io "sudo gitreceive upload-key {your-name}"
    git clone https://github.com/octohost/harp.git && cd harp
    git remote add octo git@server.octodev.io:harp-test.git
    git push octo master
    lynx http://harp-test.octodev.io

### Build your own box using Chef.

Once you have your octohost built and the box installed using [these instructions](https://github.com/octohost/octohost-cookbook)

#### Once you've built it.

Then you can cd into this directory:

    [] darron@~/Dropbox/src: cd octovagrant/
    .envrc is blocked from loading. Run `direnv allow` to approve it's content for loading.
    [] darron@~/Dropbox/src/octovagrant: direnv allow
    direnv: reloading
    direnv: loading .envrc
    direnv export: ~DOCKER_HOST
    [] darron@~/Dropbox/src/octovagrant: vagrant up
    Bringing machine 'default' up with 'virtualbox' provider...
    [default] Importing base box 'octohost'...
    [default] Matching MAC address for NAT networking...
    [default] Clearing any previously set forwarded ports...
    [default] Clearing any previously set network interfaces...
    [default] Preparing network interfaces based on configuration...
    [default] Forwarding ports...
    [default] -- 22 => 2222 (adapter 1)
    [default] Booting VM...
    [default] Waiting for machine to boot. This may take a few minutes...
    [default] Machine booted and ready!
    [default] Configuring and enabling network interfaces...
    [default] Mounting shared folders...
    [default] -- /vagrant
    [default] VM already provisioned. Run `vagrant provision` or use `--provision` to force it
    [] darron@~/Dropbox/src/octovagrant: docker ps
    CONTAINER ID        IMAGE                       COMMAND                CREATED             STATUS              PORTS                  NAMES
76d3de92d2f9        octohost/tentacles:latest   /bin/sh -c 'bundle e   15 minutes ago      Up 15 minutes       0.0.0.0:82->5000/tcp   desperate_einstein

This is in the spirit of [dvm](https://github.com/fnichol/dvm) - which is docker without the octohost web focus.

You should be able to use both dvm and [octohost](https://github.com/octohost/octohost) using these instructions.
