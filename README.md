# ASUS TUF F15 FX506LHB - Linux Mint - Postinstall

* Intel Core i5-10300H / Comet Lake
* Nvidia GTX 1650
* Meditek MT7921

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

## Update kernel
1. Run Update manager > View > Linux Kernels
2. Install last 6.2.x kernel

---

## Fix Mediatek wifi after upgrade kernel and drivers
```
sudo update-initramfs -u
```
   
---

## Install Aurora for RGB keyboard control
1. Download and install [latest .deb Aurora release](https://github.com/legacyO7/Aurora/releases/latest/)
2. Run first time as root
```
sudo aurora
```
