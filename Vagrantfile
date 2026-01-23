Vagrant.configure("2") do |config|
  GRUPO_VBOX = "/secday"
  IP_BASE = "192.168.56."

  if Vagrant.has_plugin?("vagrant-vbguest")
    config.vbguest.no_install = true
  end

  config.vm.define "ubuntu" do |ubuntu|
    ubuntu.vm.box = "SecDay/ubuntu"
    ubuntu.vm.hostname = "SIEM101-UBUNTU"
    ubuntu.vm.box_version = "1.0.1"
    ubuntu.vm.network "private_network", ip: IP_BASE + "10"
    ubuntu.vm.boot_timeout = 600
    ubuntu.vm.network "forwarded_port", guest: 22, host: 2299, protocol: "tcp", auto_correct: true
    ubuntu.ssh.username = "vagrant"
    ubuntu.ssh.password = "vagrant"
    ubuntu.ssh.insert_key = true
    ubuntu.vm.provision "shell",
      inline: "apt-get update && apt-get install virtualbox-guest-additions-iso -y && sudo apt install python3-pip -y net-tools -y"

    ubuntu.vm.provider "virtualbox" do |vb|
      vb.memory = 2048
      vb.cpus   = 2
      vb.name   = "SIEM101-Ubuntu-SecDay"
      vb.customize ["modifyvm", :id, "--groups", GRUPO_VBOX]
    end
  end

  config.vm.define "windows_2022" do |windows_2022|
    windows_2022.vm.box = "SecDay/windows_2022"
    windows_2022.vm.box_version = "1.0.0"
    windows_2022.vm.hostname = "SIEM101-WIN2022"
    windows_2022.vm.network "private_network", ip: IP_BASE + "11"
    windows_2022.vm.network "forwarded_port", guest: 3389, host: 33891, protocol: "tcp", auto_correct: true
    
    windows_2022.vm.communicator = "winrm"
    windows_2022.winrm.username = "vagrant"
    windows_2022.winrm.password = "vagrant"
    windows_2022.winrm.timeout = 600
    windows_2022.winrm.retry_limit = 30

    windows_2022.vm.provider "virtualbox" do |vb|
      vb.memory = 2048
      vb.cpus   = 2
      vb.name   = "SIEM101-Windows22-SecDay"
      vb.customize ["modifyvm", :id, "--groups", GRUPO_VBOX]
      vb.gui = false
    end
  end
end
