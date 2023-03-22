Vagrant.configure("2") do |config|
  config.hostmanager.enabled = true 
  config.hostmanager.manage_host = true



config.vm.define "nexusserver" do |nexusserver|
    nexusserver.vm.box = "generic/centos7"
    nexusserver.vm.hostname = "nexusserver"
    nexusserver.vm.network "private_network", ip: "192.168.56.16"
    nexusserver.vm.provision "shell", path: "nexus-setup.sh"
  end

config.vm.define "sonarserver" do |sonarserver|
    sonarserver.vm.box = "generic/ubuntu2010"
    sonarserver.vm.hostname = "sonarserver"
    sonarserver.vm.network "private_network", ip: "192.168.56.17"
    sonarserver.vm.provision "shell", path: "sonar-setup.sh"
  end

  config.vm.define "jenkinsserver" do |jenkinsserver|
    jenkinsserver.vm.box = "generic/ubuntu2010"
    jenkinsserver.vm.hostname = "jenkinsserver"
    jenkinsserver.vm.network "private_network", ip: "192.168.56.15"
    jenkinsserver.vm.provision "shell", path: "jenkins-install-script.sh"
  end
  
end