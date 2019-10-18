# 執行docker container可以吃到Nvidia顯示卡

首先在/etc/docker/中建立daemon.json文件

  $ sudo vi /etc/docker/daemon.json
接著輸入下列文字
{
    "runtimes": {
        "nvidia": {
            "path": "/usr/bin/nvidia-container-runtime",
            "runtimeArgs": []
        }
    }
}
