Vagrant.configure("2") do |config|
  GRUPO_VBOX = "/secday"
  IP_BASE = "192.168.56."

  config.vm.define "ubuntu" do |ubuntu|
    ubuntu.vm.box = "SecDay/ubuntu"
    ubuntu.vm.hostname = "ubuntu.local"
    ubuntu.vm.box_version = "1.0.0"
    ubuntu.vm.network "private_network", ip: IP_BASE + "10"
    ubuntu.vm.network "forwarded_port", guest: 22, host: 2221, protocol: "tcp", auto_correct: true
    ubuntu.vm.provision "shell",
      inline: "apt-get update && apt-get install virtualbox-guest-additions-iso -y && reboot"

    ubuntu.vm.provider "virtualbox" do |vb|
      vb.memory = 1024
      vb.cpus   = 1
      vb.name   = "Ubuntu-SecDay"
      vb.customize ["modifyvm", :id, "--groups", GRUPO_VBOX]
    end
  end

  config.vm.define "windows_2022" do |windows_2022|
    windows_2022.vm.box      = "SecDay/windows_2022"
    windows_2022.vm.hostname = "windows2022"
    windows_2022.vm.network "private_network", ip: IP_BASE + "11"
    windows_2022.winrm.timeout = 600
    windows_2022.vm.network "forwarded_port", guest: 3389, host: 33891, protocol: "tcp", auto_correct: true
    windows_2022.vm.communicator = "winrm"

    windows_2022.vm.provider "virtualbox" do |vb|
      vb.memory = 4096
      vb.cpus   = 2
      vb.name   = "windows_2022-SecDay"
      vb.customize ["modifyvm", :id, "--groups", GRUPO_VBOX]
    end
  end

end
