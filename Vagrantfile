
Vagrant.configure("2") do |config|
  
  
  servers=[
	{
	:hostname => "vm1",
	:box => "ubuntu/xenial64",
	:ip => "172.16.1.21",
	:ssh_port => '2221'
	},
	{
	:hostname => "vm2",
	:box => "ubuntu/xenial64",
	:ip => "172.16.1.22",
	:ssh_port => '2222'
	},
	{
	:hostname => "vm3",
	:box => "ubuntu/xenial64",
	:ip => "172.16.1.23",
	:ssh_port => '2223'
	}
  ]
  
  
  servers.each do |machine|
		config.vm.define machine[:hostname] do |node|
			node.vm.box = machine[:box]
			node.vm.hostname = machine[:hostname]
			node.vm.network :private_network, ip: machine[:ip]
			node.vm.network "forwarded_port", guest: 22, host: machine[:ssh_port], id: "ssh"

			
			#SSH
			#ssh-keygen -b 4096
			#ssh-copy-id XXX@192.168.31.236
			#ssh XXX@192.168.31.236
			#sudo nano /etc/ssh/sshd_config
			#sudo systemctl restart ssh
			
			#chmod 777 file1.txt //права доступа
			#scp root@XXX@192.168.31.237:dirlist.txt 
			#tar -cf filename.tar file1 file2 fileN
			
			#mkdir current new old 
			#tar cf myarch.tar current new old 

			
			node.vm.provision "shell", 
				
			inline: '
		
			
			',
			run: "always",
			privileged: "false"

				
			node.vm.provider :virtualbox do |vb|
				vb.gui = false
				vb.memory = 1024
				vb.cpus = 2
				
			end
				
		end
	
	end
	
end
