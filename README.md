mono-aspnetvnext Vagrant box
============================

*This repository hosts the Vagrantfile used to create the box at [https://vagrantcloud.com/akoeplinger/mono-aspnetvnext](https://vagrantcloud.com/akoeplinger/mono-aspnetvnext)*

The box contains everything needed to play with ASP.NET vNext projects on Mono.

By using Vagrant, you can run a VM with everything set up correctly without messing with your Windows, Linux or Mac OSX host.

# Requirements

* **VirtualBox**: [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)
* **Vagrant**: [http://www.vagrantup.com/downloads.html](http://www.vagrantup.com/downloads.html)

# Setup Vagrant box
To use the box and run the included "Hello World" sample, follow these steps:

1. Run `vagrant init akoeplinger/mono-aspnetvnext` in an empty directory, this creates a new Vagrantfile
2. Add `config.vm.network "forwarded_port", guest: 8080, host: 8080` to the newly created Vagrantfile to forward your local port 8080 to the VM
3. Run `vagrant up` to download the Vagrant box and boot the VM
4. Run `vagrant ssh` to connect to the VM
5. `cd helloworld/src/helloworldweb`
6. Start the test web server by running `k web`

The "Hello World" web application should now be running, access it by browsing to http://localhost:8080.

The folder containing the Vagrantfile is automatically mapped to the VM path `/vagrant`. This is a simple way to share your own projects with the VM.