# Nvidia-setup
Ubuntu 22.04 + Nvidia driver 535.86.10 + CUDA 12.2

## Check Environment

check nvidia graphics

```
lspci | grep -i nvidia
```

check Ubuntu verision

```
lsb_release -a
```

## Install Nvidia driver

Installation Guide [[reference]](https://www.alibabacloud.com/help/zh/elastic-gpu-service/latest/install-a-gpu-driver-on-a-linux-gpu-accelerated-compute-optimized-instance?spm=a2c63.p38356.0.0.67783b8b6Ro4cb#concept-ecy-qrz-wgb))

Download nvidia driver [[reference]](https://www.nvidia.com/Download/Find.aspx?spm=a2c63.p38356.0.0.6d6f2e06qAo00I&lang=cn)

(OS: Linux 64-bit)

```
wget https://us.download.nvidia.com/tesla/470.161.03/NVIDIA-Linux-x86_64-470.161.03.run

chmod +x NVIDIA-Linux-x86_64-xxxx.run

sh NVIDIA-Linux-x86_64-xxxx.run

nvidia-smi
```

## Install CUDA 

[[reference]](https://gist.github.com/Mahedi-61/2a2f1579d4271717d421065168ce6a73)

### Update & upgrade
```shell
sudo apt update && sudo apt upgrade
```

### Install CUDA toolkit
```shell
sudo apt install nvidia-cuda-toolkit
```

### Check CUDA install
```shell
nvcc --version
```

## Install cuDNN 8

[[reference]](https://gist.github.com/denguir/b21aa66ae7fb1089655dd9de8351a202)

### Download cuDNN .deb file
You can download cuDNN file [here](https://developer.nvidia.com/rdp/cudnn-download). You will need an Nvidia account.
Select the cuDNN version for the appropriate CUDA version, which is the version that appears when you run:
```shell
nvcc --version
```

### Install cuDNN
```shell
sudo apt install ./<filename.deb>
sudo cp /var/cudnn-<something>.gpg /usr/share/keyrings/
```

My cuDNN version is 8, adapt the following to your version:

```shell
sudo apt update
sudo apt install libcudnn8
sudo apt install libcudnn8-dev
sudo apt install libcudnn8-samples

## Python Virtual Environment

```python3 -m venv environment-name```

```source environment-name/bin/activate```

[How to install pip for Python 3.6 on Ubuntu 16.10?](https://askubuntu.com/questions/889535/how-to-install-pip-for-python-3-6-on-ubuntu-16-10)

[Dealing with multiple Python versions and PIP?](https://stackoverflow.com/questions/2812520/dealing-with-multiple-python-versions-and-pip)
