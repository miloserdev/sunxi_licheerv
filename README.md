# Sunxi LicheeRV D1
LicheeRV D1 Kernel and U-Boot  

Big thanks for [Samuel Holland](https://github.com/smaeul) and [Sehraf](https://github.com/sehraf)  

<img width="100%" src="https://github.com/miloserdev/sunxi_licheerv/assets/37951044/ad53bdae-f334-47b5-8f4e-e6c8a612bcac"/>  

<br><br>

# Links
https://github.com/miloserdev/linux_sunxi_licheerv  
https://github.com/miloserdev/u-boot_sunxi_licheerv  
https://github.com/sehraf/d1-riscv-arch-image-builder  
https://archriscv.felixc.at/
<br><br>

# Install

```console
git clone https://github.com/miloserdev/sunxi_licheerv.git
cd ./sunxi_licheerv
./create_sd.sh /dev/mmcblk0
```
  
> **After install:** you may install some packages like **NetworkManager** and etc.  
  
Default login `root` and password `archriscv`  
  

<br><br>

# Wiki

## Leds gpio

### Green led onboard
brightness `0-1`
```console
echo 1 > /sys/class/leds/green\:status/brightness
```

### SPI ws2812 RGB led on dock
brightness `0-255`  
```console
echo "255" > /sys/class/leds/rgb\:status/brightness
```

R G B `0-255 0-255 0-255` 
```console
echo "10 10 10" > /sys/class/leds/rgb\:status/multi_intensity  
```

<br>

## 1.14 inch st7789v Display
> Requires fbida package  
Show image on the display  
```console
fbi -d /dev/fb0 -T 1 -noverbose -a ./riscv.jpg
```

