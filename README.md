# ubuntu16.04
# nvidia-docker
# 安裝docker-ce：
#     sudo apt-get install docker-ce docker-ce-cli containerd.io
# 參考網址：https://docs.docker.com/install/linux/docker-ce/ubuntu/
# 安裝nvidia-docker：
     $ distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
     $ curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -
     $ curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list
     $ sudo apt-get update && sudo apt-get install -y nvidia-container-toolkit
     $ sudo systemctl restart docker
# 參考網址：https://github.com/NVIDIA/nvidia-docker

# nvidia-docker-compose
# 安裝指令：pip install nvidia-docker-compose
# 參考網址：https://github.com/eywalker/nvidia-docker-compose
