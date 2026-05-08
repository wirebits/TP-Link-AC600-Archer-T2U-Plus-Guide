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