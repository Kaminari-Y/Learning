# Install Vagrant on Windows
### Install VirtualBox
      https://www.virtualbox.org/
download virtualbox and install, nothing difficult.

### Install Vagrant
    http://www.vagrantup.com/
as above, nothing difficult. You can run this to check out the version of Vagrant.

    vagrant -v
### Install VirtualBox's VM
    http://www.vagrantbox.es/
choose the OS you need. And add to you box
    vagrant box add {name} {url}

##### Example
install ubuntu1410

    vagrant box add ubuntu1410 https://github.com/kraksoft/vagrant-box-ubuntu/releases/download/14.10/ubuntu-14.10-amd64.box
    vagrant init ubuntu1410　#initialization
    vagrant up # start
    vagrant halt #stop
    vagrant destroy #terminate

### Configure vagrantfile
change the file like below

    Vagrant.configure(2) do |config|
      config.vm.box = "ubuntu1410"
      config.vm.network "forwarded_port", guest: 80, host: 8080
      config.vm.network "private_network", ip: "192.168.33.11"
      config.vm.synced_folder "../share_with_vagrant", "/vagrant_data"
      config.vm.provider "virtualbox" do |vb|
      vb.gui = true
      end
    end

### Boot
