# 執行docker container可以吃到Nvidia顯示卡

首先在/etc/docker/中建立daemon.json文件：

     $ sudo vi /etc/docker/daemon.json
接著輸入下列文字在後面：

      {
          "runtimes": {
              "nvidia": {
                  "path": "/usr/bin/nvidia-container-runtime",
                  "runtimeArgs": []
              }
          }
      }
接著重啟docker：

      $ systemctl restart docker
      $ systemctl status docker

之後可以去https://hub.docker.com/r/nvidia/cuda/找自己需要的docker images檔案
下列以"10.1-cudnn7-devel-ubuntu16.04" docker images檔案做為示範：
請執行此指令，把container run起來：

      $ sudo docker run -it --runtime=nvidia nvidia/cuda:10.1-cudnn7-devel-ubuntu16.04
進入容器後下此指令：

      $ nvidia-smi

如果有看到東西就成功了 !! 恭喜
