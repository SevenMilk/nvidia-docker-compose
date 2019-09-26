# 系統 ubuntu16.04 記錄安裝nvidia-docker & nvidia-docker-compose
在安裝nvidia-docker前必須先安裝docker-ce


刪除舊版本的docker：

     $ sudo apt-get remove docker docker-engine docker.io containerd runc
如果無法刪除可以按照下列方法


參考網址：

     $ https://askubuntu.com/questions/935569/how-to-completely-uninstall-docker
To completely uninstall Docker:


Step 1

     $ dpkg -l | grep -i docker
To identify what installed package you have:


Step 2

     $ sudo apt-get purge -y docker-engine docker docker.io docker-ce  
     $ sudo apt-get autoremove -y --purge docker-engine docker docker.io docker-ce  
The above commands will not remove images, containers, volumes, or user created configuration files on your host. If you wish to delete all images, containers, and volumes run the following commands:

     $ sudo rm -rf /var/lib/docker /etc/docker
     $ sudo rm /etc/apparmor.d/docker
     $ sudo groupdel docker
     $ sudo rm -rf /var/run/docker.sock
You have removed Docker from the system completely.

安裝docker-ce：

     $ sudo apt-get install docker-ce docker-ce-cli containerd.io
參考網址：

     $ https://docs.docker.com/install/linux/docker-ce/ubuntu/
安裝nvidia-docker：

     $ distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
     $ curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -
     $ curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list
     $ sudo apt-get update && sudo apt-get install -y nvidia-container-toolkit
     $ sudo systemctl restart docker
這時候如果打下列command是沒反應代表安裝失敗，請重新安裝!

     $ sudo systemctl restart nvidia-docker
參考網址：

     $ https://github.com/NVIDIA/nvidia-docker

# nvidia-docker-compose
# 安裝指令：pip install nvidia-docker-compose
# 參考網址：https://github.com/eywalker/nvidia-docker-compose
