Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/jammy64"  # Ubuntu 22.04
  config.vm.network "private_network", ip: "192.168.56.10"  # IP fixe pour accès facile
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "4096"  # 4GB RAM
    vb.cpus = 2  # 2 cœurs CPU
  end
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt update
    sudo apt install -y docker.io curl  # Installe Docker et curl
    sudo systemctl start docker
    sudo systemctl enable docker
    sudo usermod -aG docker vagrant  # Ajoute l'utilisateur vagrant au groupe Docker
  SHELL
end
