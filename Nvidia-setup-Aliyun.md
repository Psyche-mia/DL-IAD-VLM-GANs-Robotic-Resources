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

(Linux 64-bit)

```
wget https://us.download.nvidia.com/tesla/470.161.03/NVIDIA-Linux-x86_64-470.161.03.run

chmod +x NVIDIA-Linux-x86_64-xxxx.run

sh NVIDIA-Linux-x86_64-xxxx.run

nvidia-smi
```

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

[[reference]](https://medium.com/repro-repo/install-cuda-10-1-and-cudnn-7-5-0-for-pytorch-on-ubuntu-18-04-lts-9b6124c44cc)

In order to download cuDNN you have to be regeistered here https://developer.nvidia.com/developer-program/signup
then download cuDNN v7.5.0 form https://developer.nvidia.com/cudnn

Download all 3 .deb files: the runtime library, the developer library, and the code samples library for Ubuntu 18.04.

In your download folder, install them in the same order:

```
sudo dpkg -i libcudnn7_7.5.0.56–1+cuda10.0_amd64.deb (the runtime library)

sudo dpkg -i libcudnn7-dev_7.5.0.56–1+cuda10.0_amd64.deb (the developer library)

sudo dpkg -i libcudnn7-doc_7.5.0.56–1+cuda10.0_amd64.deb (the code samples)

```

Now we can verify the cuDNN installation (below is just the official guide, which surprisingly works out of the box):
Go to the MNIST example code: 

```cd /usr/src/cudnn_samples_v7/mnistCUDNN/.```

Compile the MNIST example: 

```sudo make clean && sudo make.```

Run the MNIST example: 
```./mnistCUDNN ```

If your installation is successful, you should see Test passed! at the end of the output.

## Python Virtual Environment

```python3 -m venv environment-name```

```source environment-name/bin/activate```

[How to install pip for Python 3.6 on Ubuntu 16.10?](https://askubuntu.com/questions/889535/how-to-install-pip-for-python-3-6-on-ubuntu-16-10)

[Dealing with multiple Python versions and PIP?](https://stackoverflow.com/questions/2812520/dealing-with-multiple-python-versions-and-pip)
