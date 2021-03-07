# How to activate UART1 interface Firefly ROC-3288-CC board


1. Upload dts file to /home directory.

2. Convert dts to dtbo overlay format:
sudo dtc -I dts -O dtb -o rockchip-uart1.dtbo rockchip-uart1.dts

3. Copy dtbo file to overlay folder:
sudo cp rockchip-uart1.dtbo /boot/dtb/rockchip/overlay/rockchip-uart1.dtbo

4. Change owner:
sudo chown root:root  /boot/dtb/rockchip/overlay/rockchip-uart1.dtbo

5. Change permission:
sudo chmod 755 /boot/dtb/rockchip/overlay/rockchip-uart1.dtbo

6. Reboor you'r Firefly ROC-3288-CC board

7. Run armbian-config and toggle UART1 in 'periferal' section.

8. Add current user to appropriate group:
sudo usermod -a -G dialout $USER
sudo usermod -a -G tty $USER
sudo usermod -a -G uucp $USER

Done
