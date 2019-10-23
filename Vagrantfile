$script_centos = <<SCRIPT
sudo yum update -y && sudo yum upgrade -y
SCRIPT

$script_debian = <<SCRIPT
sudo apt-get update -y && sudo apt-get upgrade -y
SCRIPT

Vagrant.configure("2") do |config|
  
  #config.vm.define "manager" do |manager|
    #manager.vm.provider :hyperv do |hyperv|
      #hyperv.vmname = "manager"
      #hyperv.memory = 1024
      #hyperv.cpus = 2
    #end
    #manager.vm.box = "generic/debian9"
    #manager.vm.hostname = "manager"
    #manager.vm.network "private_network", bridge: "Swisscom", ip: "192.168.1.150"
    #manager.vm.provision "shell", inline: $script_debian
  #end
  
  config.vm.define "http1" do |http1|
    http1.vm.provider :hyperv do |hyperv|
      hyperv.vmname = "http1"
      hyperv.memory = 1024
      hyperv.cpus = 1
    end
    http1.vm.box = "centos/7"
    http1.vm.hostname = "http1"
    http1.vm.network "private_network", bridge: "Swisscom", ip: "192.168.1.151"
    http1.vm.provision "shell", inline: $script_centos
  end
  
  config.vm.define "bdd1" do |bdd1|
    bdd1.vm.provider :hyperv do |hyperv|
      hyperv.vmname = "bdd1"
      hyperv.memory = 1024
      hyperv.cpus = 1
    end
    bdd1.vm.box = "centos/7"
    bdd1.vm.hostname = "bdd1"
    bdd1.vm.network "private_network", bridge: "Swisscom", ip: "192.168.1.152"
    bdd1.vm.provision "shell", inline: $script_centos
  end

end
