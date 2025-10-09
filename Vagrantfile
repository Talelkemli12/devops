Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"  # Box Ubuntu 20.04
  config.vm.network "forwarded_port", guest: 8080, host: 8080  # Jenkins
  config.vm.network "forwarded_port", guest: 80, host: 8081  # Apps
  config.vm.network "private_network", ip: "192.168.33.10"  # IP fixe
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "4096"  # 4GB RAM
    vb.cpus = 4  # 4 CPUs
  end
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y apt-transport-https ca-certificates curl software-properties-common
  SHELL
end
