
Vagrant.configure("2") do |config|

  # configures the vm
  config.vm.box = "ubuntu/xenial64"
  config.vm.network "private_network", ip:"192.168.10.100"

  #provision the vm to have nginx
  config.vm.provision "shell", path: "prov.sh"

  #Put the app folder from local machine to the VM
  config.vm.synced_folder "app", "/home/vagrant/app"
  

end