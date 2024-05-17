# OLLAMA

SETUP WSL (WINDOWS)
Install WSL and Ubuntu
wsl --install
wsl cat /proc/version

Connect to a WSL Instance in a new window
wsl -d Ubuntu

sudo apt install nvidia-driver-XXX
sudo apt install ubuntu-drivers-common
sudo apt-get update && sudo apt-get upgrade

Only if it doesn't work-
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt-get update
sudo apt install linux-headers-$(uname -r)


sudo ubuntu-drivers autoinstall
sudo apt install nvidia-driver-XXX

https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=WSL-Ubuntu&target_version=2.0&target_type=runfile_local
wget https://developer.download.nvidia.com/compute/cuda/12.4.1/local_installers/cuda_12.4.1_550.54.15_linux.run
chmod +x cuda_12.4.1_550.54.15_linux.run
sudo apt update
sudo apt install gcc dkms -y
gcc --version



sudo ./cuda_12.4.1_550.54.15_linux.run --silent --driver



https://www.bing.com/videos/search?q=install+cuda+12.4.1+on+windows+11+wsl+ubuntu+22.04&view=detail&mid=56A4A77476026AE65B6D56A4A77476026AE65B6D&FORM=VIRE

curl -fsSL https://ollama.com/install.sh | sh

INSTALL OLLAMA
https://ollama.com/download

Add a model to Ollama
ollama pull llama2
ollama pull codegemma
 

"WATCH" GPU PERFORMANCE IN LINUX
watch -n 0.5 nvidia-smi

 

INSTALL DOCKER
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
$(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

#Install Dockersudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

RUN OPEN WEBUI DOCKER CONTAINER
docker run -d --network=host -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --name open-webui --restart always ghcr.io/open-webui/open-webui:main

 

STABLE DIFFUSION INSTALL
Prereqs
Pyenv
#Install Pyenv prereqssudo apt install -y make build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev \
libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev git

#Install Pyenv

curl https://pyenv.run | bash

#Install Python 3.10

pyenv install 3.10

#Make it global

pyenv global 3.10
