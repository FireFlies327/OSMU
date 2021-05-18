
Vagrant.configure("2") do |config|
  
  
  servers=[
	{
	:hostname => "VM1",
	:box => "ubuntu/xenial64",
	:ip => "172.16.1.50",
	:ssh_port => '2200'
	},
		{
	:hostname => "VM2",
	:box => "ubuntu/xenial64",
	:ip => "172.16.1.51",
	:ssh_port => '2201'
	}
  ]
  
  
  servers.each do |machine|
		config.vm.define machine[:hostname] do |node|
			node.vm.box = machine[:box]
			node.vm.hostname = machine[:hostname]
			node.vm.network :private_network, ip: machine[:ip]
			node.vm.network "forwarded_port", guest: 22, host: machine[:ssh_port], id: "ssh"
			node.vm.synced_folder "c:/VM'S/VagrantVM", "/var/www"
			
			#node.disksize.size = "10GB"
			
			
			
			#node.vm.provision "shell", 
			#inline: "
			#sudo apt-get update
			#sudo apt-get install git
			#git init .
			#git remote add -f origin https://github.com/FireFlies327/OSMU
			#git checkout lab3
			#git show :task3.txt
			#git remote
			
			#обновление локального репозитория
			#git remote update origin --prune
			#git pull
			
			#
	#Пункт2
			#установка 
			
				#sudo apt-get update
				#sudo apt-get install apt-transport-https ca-certificates
				#sudo apt-key adv — keyserver hkp://p80.pool.sks-keyservers.net:80 — recv-keys 58118E89F3A912897C070ADBF76221572C52609D
				#sudo cat /etc/apt/sources.list.d/docker.list<<EOF
				#deb https://apt.dockerproject.org/repo ubuntu-xenial main
				#EOF
				#
				#sudo apt-get purge lxc-docker
				#sudo apt-cache policy docker-engine
				#
				#sudo apt-get install linux-image-extra-$(uname -rsu)
				#
				#sudo apt-get install docker.io
				#sudo service docker start
				#
				#sudo docker run hello-world
				
				#вывод на экран тестовый образ
				#docker run hello-world
				
				#поиск пакета
				#docker search ubuntu

			#Для загрузки образа на локальный компьютер
			#docker pull ubuntu
			
			#зайти в консоль первой машины
			#vagrant ssh vm1
			
			#docker images //просмотр образов
			#sudo docker images -q
			
			#запуск образа
			#docker run ubuntu
			#Для запуска нового контейнера используется команда
			#docker run --name MyContainer -it ubuntu bash
			
			#для запуска существующего контейнера
			#sudo docker start MyContainer
			
			#остановка контейнера
			#sudo docker stop MyContainer sudo docker kill wonderful_kapitsa
			
			
			#просмотр существующих(запущенных) контейнеров
			#docker ps -all
			#docker container ls -all
			
			#sudo docker start ecc69fc8a431 
			#sudo docker start d16c0969f195
			#docker ps -a
			#docker info		
			
	#Пункт 3
			#sudo dockerd --debug
			#sudo systemctl stop docker
			#sudo cp -au /var/lib/docker /var/lib/docker.bk
			#echo '{ "storage-driver": "devicemapper" }' | sudo tee /etc/docker/daemon.json
			#sudo systemctl start docker
			#sudo systemctl status docker.service
			
			#sudo systemctl stop docker
			#sudo apt-get install -y thin-provisioning-tools
			
	#Пункт 4	
	
			#создание дисков
			#sudo -s //права root
			#fdisk -l //fdisk — это утилита командной строки для просмотра и управления жесткими дисками и разделами в системах Linux
			#cat /proc/partitions //проверка существования дисков
			#fdisk /dev/sdb //разбиение диска
			#echo 'n, p, 1, 2048, +10G, w'
			#mkfs.ext4 /dev/sdb1

			#dd if=/dev/sdc of=/dev/sdd bs=64K conv=noerror,sync //copy new disk
			
			
			#для объединения в raid
			#sudo -s
			#sudo apt-get install mdadm
			#sudo mdadm --examine /dev/sdb 
			#sudo mdadm --examine /dev/sdb1 /dev/sdb2
			#sudo mdadm --create /dev/md0 --level=mirror --raid-devices=2 /dev/sdb1 /dev/sdb2 //создание raid
			#sudo mkfs.ext4 /dev/md0
			#sudo mkdir /mnt/raid1
			#sudo mount /dev/md0 /mnt/raid1
			#df -h /mnt/raid1 //занимаемое пространство raid
			
			
			#Редактируем файл sudoers
			#sudo visudo -f /etc/sudoers
			#%sudo   ALL=(ALL:ALL)NOPASSWD:ALL //убираем ввод пароля
			
			#Управление группами и пользователями 
			#sudo groupadd mygroup //создаём группу
			#sudo adduser -m alex //создаём пользователя
			#sudo usermod -G -a newgroup alex
			#sudo delgroup mygroup //удаляем группу
			
			
			node.vm.provision "shell", 
			inline: "	
		
			
			",
			run: "always",
			privileged: "false"
			
			#node.vm.disk :disk, size: "10GB", primary: true
			#node.vm.provider :virtualbox do |vb|
				#vb.customize ["modifyvm", :id, "--memory", 1024]
				#vb.customize ["modifyvm", :id, "--cpus", 2]
				
			node.vm.provider :virtualbox do |vb|
				vb.gui = false
				vb.memory = 1024
				vb.cpus = 2
				
			end
				
		end
	
	end
	
end
