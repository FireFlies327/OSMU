$script = <<-SHELL
                    sudo apt-get install git -y
                    wget https://raw.githubusercontent.com/FireFlies327/OSMU/main/text.txt
                    cat text.txt
                    ping -c 4 192.168.1.1
                    ping -c 4 192.168.1.2
                    SHELL


Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.box_check_update = false


  config.vm.define "KrasukUb1" do |vm1|
      vm1.vm.network  "public_network", ip: "192.168.1.10"
      vm1.vm.hostname = "KrasukUb1"
      vm1.vm.provider "virtualbox" do |vb|
         vb.memory = "4096"
      end
      vm1.vm.provision "shell",
                    inline: "sudo apt-get install git -y"
      vm1.vm.provision "shell",
                    inline: "wget https://raw.githubusercontent.com/FireFlies327/OSMU/main/text.txt"
      vm1.vm.provision "shell",
                    inline: "cat text.txt"
  end


 config.vm.define "KrasukUb2" do |vm2|
     vm2.vm.network "public_network", ip: "192.168.1.11"
     vm2.vm.hostname = "KrasukUb2"
     vm2.vm.provider "virtualbox" do |vb|
         vb.memory = "1024"
     end
      vm2.vm.provision "shell",
                    inline: "sudo apt-get install git -y"
      vm2.vm.provision "shell",
                    inline: "wget https://raw.githubusercontent.com/FireFlies327/OSMU/main/text.txt"
      vm2.vm.provision "shell",
                    inline: "cat text.txt"
      vm2.vm.provision "shell",
                    inline: "ping -c 4 192.168.1.10"
 end

end
