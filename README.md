# ASUS TUF F15 FX506LHB - Linux Mint - Postinstall

### Not working
* Fn+left & Fn+right: Aura control
* Fn+F5: Fan control

---

## Remove ACPI errors
1. Install Grub Customizer
```
sudo add-apt-repository ppa:danielrichter2007/grub-customizer
sudo apt update
sudo apt install grub-customizer -y
```
2. Open Grub Customizer > General Settings > Kernel parameters
```
quiet splash loglevel=3 fbcon=nodefer video=efifb:nobgrt
```

---

## Install [XanMod Kernel](https://xanmod.org/)
```
wget -qO - https://dl.xanmod.org/archive.key | sudo gpg --dearmor -o /usr/share/keyrings/xanmod-archive-keyring.gpg
echo 'deb [signed-by=/usr/share/keyrings/xanmod-archive-keyring.gpg] http://deb.xanmod.org releases main' | sudo tee /etc/apt/sources.list.d/xanmod-release.list
sudo apt update
sudo apt install linux-xanmod-x64v3
```

