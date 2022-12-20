# Aleo on docker

Login to rent GPUs https://bit.ly/rentgpu

Click **CLIENT** > **Create** > **Edit Image & Config...**

Select Docker Image: `ubuntu:20.04`
![image](https://user-images.githubusercontent.com/102939807/208360292-2f8b6430-5520-4adb-8126-2ea401caf03c.png)


SSH to the instance just created

`#` Run commands below

    apt update -y; apt upgrade -y; apt install cron vim cmake curl libssl-dev libclang-dev git-all wget -y
    
    curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- --profile default
<br/>

    source "$HOME/.cargo/env"; rustup update stable

`#` Install cuda
  
    apt install kmod nvidia-cuda-toolkit -y

`#` Check version

    nvidia-smi

`#` Download damomine

    wget https://github.com/damomine/aleominer/releases/download/v2.1.2/damominer_linux_v2.1.2.tar
    tar -xvf damominer_*.tar ; chmod +x damominer

`#` Run damonine, change your aleoaleoaddressxxxxxxxxxxxxxxxxxxxxx

    ./damominer --address <aleoaddressxxxxxxxxxxxxxxxxxxxxx> --proxy aleo1.damominer.hk:9090 >> aleo.log 2>&1 &

`#` check log

    tail -f aleo.log
`#` check reward

https://www.damominer.hk  
https://www.aleo.network  
https://aleo123.io  
https://explorer.hamp.app  
