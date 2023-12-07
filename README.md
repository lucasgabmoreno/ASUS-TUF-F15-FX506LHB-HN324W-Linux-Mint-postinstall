# ASUS TUF F15 FX506LHB - Linux Mint - Postinstall

* Intel Core i5-10300H / Comet Lake
* Nvidia GTX 1650
* Meditek MT7921

### Not working
* `Fn + Left` & `Fn + Right`: Aura control
* `Fn + F5`: Fan control

---

## BIOS config
1. Turn On > `F2`
2. Advance mode(F7) > Boot > Base boot > `disabled`
3. Advance mode(F7) > Security > Secure boot > Secure boot controñ > `disabled`
   
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
2. Install last 6.1 + kernel

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

---

## Battery
```
git clone https://github.com/AdnanHodzic/auto-cpufreq.git
cd auto-cpufreq && sudo ./auto-cpufreq-installer
```
> Option "i"
```
sudo auto-cpufreq --install
```

---

## Replace Meditek MT7921
* Intel 6E AX210
* Broadcom BCM94350ZAE / DW 1820A
> If Broadcom, use this [driver installer](https://github.com/lucasgabmoreno/bashinstallers/tree/main/bcm43x)
