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
3. Advance mode(F7) > Security > Secure boot > Secure boot control > `disabled`
   
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

## Wifi not working
### Compatible wifi cards, same problems:
* Intel 6E AX210
* Broadcom BCM94350ZAE / DW 1820A
### Temporary fix:
1. Press power button for 30 seconds
2. Reboot
3. If keyboard isn't working, reboot again
### Permanent fix:
1. Open notebook and unmount wifi card
2. Use electrical insulate tape and cover these 3 pins at front and 2 pins back:
<img src="img/DW1820A_Cover_pins.jpg">
3. This will cause not to get sleep your wifi card. It is not 100% permanent. If you experience a Wi-Fi drop, use the temporary method again by turning off for 30 seconds.
   
---

## Install Aurora for RGB keyboard control
1. Download and install [latest .deb Aurora release](https://github.com/legacyO7/Aurora/releases/latest/)
2. Run first time as root
```
sudo aurora
```

---

## Battery life
Improve battery life
```
git clone https://github.com/AdnanHodzic/auto-cpufreq.git
cd auto-cpufreq && sudo ./auto-cpufreq-installer
```
> Option "i"
```
sudo auto-cpufreq --install
```
