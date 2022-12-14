# Ubuntu Erros

### Ubuntu 22.04 : No display signal from device

Actually I have installed Ubuntu 22.04 on a fresh new HP Zbook Fury with the same GPU as yours. Hence I make the assumption that we share the configuration. Apparently, HDMI port is not working with the Intel integrated graphics using Linux drivers. In order to make it work, you can fresh install new NVIDIA drivers with the following commands:

```
sudo add-apt-repository ppa:graphics-drivers/ppa -y
sudo apt update
ubuntu-drivers devices
```

Now you can see the recommended drivers and the name of your GPU. Personally the recommended one (nvidia-520-open) crashed my computer so simply use:

```
sudo apt install nvidia-driver-520
reboot
``

Normally, the second monitor should work as a charm and you can leave your BIOS to hybrid mode for GPU.

Futhermore, you could install nvidia-prime via the Ubuntu extension manager in order to switch between GPU (eg. Intel for battery life and NVIDIA for processing... even if you can select the NVIDIA on demand option)

Hope it solves your problem ;)
