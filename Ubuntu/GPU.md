# Setting GPU Device for Jupyter Notebook on Ubuntu WSL2

https://saturncloud.io/blog/how-to-make-jupyter-notebook-to-run-on-gpu/

Installation Instructions:
```
wget https://developer.download.nvidia.com/compute/cuda/repos/wsl-ubuntu/x86_64/cuda-keyring_1.1-1_all.deb
sudo dpkg -i cuda-keyring_1.1-1_all.deb
sudo apt-get update
sudo apt-get -y install cuda
```