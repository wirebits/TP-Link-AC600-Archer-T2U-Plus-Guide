# TP-Link-AC600-Archer-T2U-Plus-Guide
A guide to install drivers of TP-Link AC600 Archer T2U Plus on Kali Linux.

`amd64` - PC/Laptop/VMs of 64-Bit
`arm64` - Raspberry Pi, Orange Pi, Banana Pi etc of 64-Bit.

# There are 2 ways to install drivers on Kali Linux
## Way-1
1. Update and Upgrade the Linux System
```
sudo apt update && sudo apt full-upgrade -y
```
2. Install driver for the chipset `RTL8821AU`
```
sudo apt install realtek-rtl88xxxau-dkms -y
```
3. Reboot the system
```
sudo reboot
```
4. Now, the adapter is working properly.
## Way-2
1. Update and Upgrade the Linux System
```
sudo apt update && sudo apt full-upgrade -y
```
2. Check Kernel Version
```
uname -r
```
3. Go to this website
```
https://kali.download/kali/pool/main/l/linux/
```
4. Download 3 files with following similiar names and kernel version of your system
```
linux-headers-X.X.X+kali-common_X.X.X-1kali1_all.deb
```
For `amd64`
```
linux-kbuild-X.X.X+kali_X.X.X-1kali1_amd64.deb
```
For `arm64`
```
linux-kbuild-X.X.X+kali_X.X.X-1kali1_arm64.deb
```
For `amd64`
```
linux-headers-X.X.X+kali-amd64_X.X.X-1kali1_amd64.deb
```
For `arm64`
```
linux-headers-X.X.X+kali-arm64_X.X.X-1kali1_arm64.deb
```
`X.X.X` is the kernel version.
5. Put all 3 files in a folder.
6. Run the following commands one by one
```
sudo dpkg -i linux-headers-X.X.X+kali-common_X.X.X-1kali1_all.deb
```
For `amd64`
```
sudo dpkg -i linux-kbuild-X.X.X+kali_X.X.X-1kali1_amd64.deb
```
For `arm64`
```
sudo dpkg -i linux-kbuild-X.X.X+kali_X.X.X-1kali1_arm64.deb
```
For `amd64`
```
sudo dpkg -i linux-headers-X.X.X+kali-amd64_X.X.X-1kali1_amd64.deb
```
For `arm64`
```
sudo dpkg -i linux-headers-X.X.X+kali-arm64_X.X.X-1kali1_arm64.deb
```
7. Download driver files for chipset `RTL8821AU`
```
git clone https://github.com/morrownr/8821au-20210708.git
```
8. Go to the `8821au-20210708` folder.
```
cd 8821au-20210708
```
9. Install `bc` tool
```
sudo apt install bc -y
```
10. Run the script to compile, build and install drivers according to your kernel
```
sudo sh install-driver.sh
```
- Wait for sometime to complete.
- It ask for edit driver option file and here type `n`.
- It ask for rebooting and here type `y`.
11. Now, the adapter is working properly.
