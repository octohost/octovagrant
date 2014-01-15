octovagrant
===========

Some helpful files when using octohost with Vagrant.

    # Install Docker Mac binary
    brew tap homebrew/binary
    brew install docker
    brew install direnv # More info here: https://github.com/zimbatm/direnv
    
Once you have your octohost built and the box installed using [these instructions](https://github.com/octohost/octohost-cookbook)

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
    CONTAINER ID        IMAGE                           COMMAND                CREATED             STATUS              PORTS                     NAMES
    22fefafea8c7        octohost/app2.git-app2:latest   /usr/local/bin/forem   23 minutes ago      Up 23 minutes       0.0.0.0:49154->5000/tcp   happy_bardeen       
    7a1463f538df        octohost/app1:latest            /usr/local/bin/forem   24 minutes ago      Up 24 minutes       0.0.0.0:49153->5000/tcp   drunk_fermat
    [] darron@~/Dropbox/src/octovagrant: docker ps -a
    CONTAINER ID        IMAGE                           COMMAND                CREATED             STATUS              PORTS                     NAMES
    619a461ab9fe        octohost/app3.git-app3:latest   /usr/local/bin/forem   6 minutes ago       Exit 0                                        hopeful_brown         
    f06e8317f36c        a94a8b900af9                    /bin/sh -c #(nop) CM   6 minutes ago       Exit 0                                        clever_mclean         
    ea92fee575ca        2820723ae575                    /bin/sh -c #(nop) EX   6 minutes ago       Exit 0                                        determined_torvalds   
    2084adde2488        bbeff4040bf9                    /bin/sh -c cd /srv/w   7 minutes ago       Exit 0                                        romantic_bardeen      
    80ce783396f2        octohost/ruby-1.9:latest        /bin/sh -c #(nop) AD   7 minutes ago       Exit 0                                        furious_morse         
    09f34b053a05        7b923571220a                    /usr/local/bin/forem   8 minutes ago       Exit 0                                        elegant_babbage       
    7e22fdd248ea        b21b1a012bc7                    /bin/sh -c #(nop) CM   8 minutes ago       Exit 0                                        boring_mccarthy       
    2e0bf12fda57        24c803e0e2a8                    /bin/sh -c #(nop) EX   8 minutes ago       Exit 0                                        angry_brown           
    8699f8785533        36ef5f197d0d                    /bin/sh -c cd /srv/w   8 minutes ago       Exit 0                                        sick_fermi            
    4360d8012b29        octohost/ruby-2.0:latest        /bin/sh -c #(nop) AD   8 minutes ago       Exit 0                                        romantic_pike         
    e16653ac4934        7d1caf4fc491                    /usr/local/bin/forem   10 minutes ago      Exit 0                                        evil_turing           
    f1ef683ef0a0        7782490586af                    /bin/sh -c #(nop) CM   10 minutes ago      Exit 0                                        dreamy_nobel          
    ce7bc1e8cc44        ec96763903d9                    /bin/sh -c #(nop) EX   10 minutes ago      Exit 0                                        berserk_tesla         
    32c671292144        5f4195d3d939                    /bin/sh -c cd /srv/w   10 minutes ago      Exit 0                                        pensive_darwin        
    822e98cc4a95        octohost/ruby-2.0:latest        /bin/sh -c #(nop) AD   10 minutes ago      Exit 0                                        hungry_bohr           
    22fefafea8c7        octohost/app2.git-app2:latest   /usr/local/bin/forem   23 minutes ago      Up 23 minutes       0.0.0.0:49154->5000/tcp   happy_bardeen         
    7a1463f538df        octohost/app1:latest            /usr/local/bin/forem   24 minutes ago      Up 24 minutes       0.0.0.0:49153->5000/tcp   drunk_fermat          
    [] darron@~/Dropbox/src/octovagrant: docker logs 619a461ab9fe
    18:07:38 web.1  | started with pid 7
    18:07:38 web.1  | /srv/www/vendor/bundle/ruby/1.9.1/gems/sinatra-1.4.4/lib/sinatra/base.rb:1488:in `start_server': undefined method `run' for HTTP:Module (NoMethodError)
    18:07:38 web.1  | 	from /srv/www/vendor/bundle/ruby/1.9.1/gems/sinatra-1.4.4/lib/sinatra/base.rb:1426:in `run!'
    18:07:38 web.1  | 	from /srv/www/vendor/bundle/ruby/1.9.1/gems/sinatra-1.4.4/lib/sinatra/main.rb:25:in `block in <module:Sinatra>'
    18:07:38 web.1  | exited with code 1
    18:07:38 system | sending SIGTERM to all processes

This is in the spirit of [dvm](https://github.com/fnichol/dvm) - which is docker without the octohost web focus.

You should be able to use both dvm and [octohost](https://github.com/octohost/octohost) using these instructions.
