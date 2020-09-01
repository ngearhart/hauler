##################################
# The vagrant-vbguest plugin is required for CentOS 7.
# Run the following command to install/update this plugin:
# vagrant plugin install vagrant-vbguest
##################################

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.hostname = "airgap"
  config.vm.network "private_network", type: "dhcp"

  config.vm.synced_folder ".", "/opt/k3ama"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.cpus = "2"
  
  config.vm.provision "shell",
    run: "always",
    inline: "/opt/k3ama/vagrant-scripts/airgap.sh airgap"
  end
end
