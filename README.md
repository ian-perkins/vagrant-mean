### Creating a new Vagrant box

#### IMPORTANT: this setup was tested using Vagrant 1.9.5 and VirtualBox 5.1.22  

Clone this repo e.g. to a local directory called `vagrant`

Update the indicated line in `Vagrantfile` to suit your particular requirements.

Then: 

`cd vagrant`  
`vagrant up`  

This will take a few minutes, depending on the speed of your internet connection. 

When it finishes:

`vagrant halt`  
`sudo vagrant plugin install vagrant-vbguest`  
`vagrant up`  

This last step will cause the guest additions to be kept up-to-date. It's optional but without it, there will be a warning message each time the Vagrant machine is booted.

Finally, `ssh` into the Vagrant machine: `vagrant ssh` and `cd` into the root folder (shared between the guest and host machines). For example, if the synced folder specified in the `Vagrantfile` was changed to `/var/www/server` then `cd /var/www/server`.   

Before starting the Mongo server: `sudo mkdir -m 777 -p /data/db`   
