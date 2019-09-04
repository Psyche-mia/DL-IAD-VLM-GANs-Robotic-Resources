# Nvidia-setup
Ubuntu 18.04 + Nvidia driver 430.40 + CUDA 10.0 + cuDNN 7.5

## Install Nvidia driver

- **Auto-install driver** [[reference]](https://askubuntu.com/questions/1028830/how-do-i-install-cuda-on-ubuntu-18-04)
```
sudo add-apt-repository ppa:graphics-drivers/ppa

sudo apt update

sudo ubuntu-drivers autoinstall
```
reboot

## Install CUDA 10.0

[[reference]](https://gist.github.com/Mahedi-61/2a2f1579d4271717d421065168ce6a73)

```
 # installing CUDA-10.0
sudo apt-get -o Dpkg::Options::="--force-overwrite" install cuda-10-0 cuda-drivers


# setup your paths
echo 'export PATH=/usr/local/cuda-10.0/bin:$PATH' >> ~/.bashrc
echo 'export LD_LIBRARY_PATH=/usr/local/cuda-10.0/lib64:$LD_LIBRARY_PATH' >> ~/.bashrc
source ~/.bashrc
sudo ldconfig
```
## Install cuDNN 7.5

In order to download cuDNN you have to be regeistered here https://developer.nvidia.com/developer-program/signup
then download cuDNN v7.5 form https://developer.nvidia.com/cudnn
