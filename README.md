# Sunxi LicheeRV D1
LicheeRV D1 Kernel and U-Boot  

Big thanks for [Samuel Holland](https://github.com/smaeul) and [Sehraf](https://github.com/sehraf)  

<img width="50%" src="https://github.com/miloserdev/sunxi_licheerv/assets/37951044/ad53bdae-f334-47b5-8f4e-e6c8a612bcac"/>  

<br><br>

# Links
https://github.com/miloserdev/linux_sunxi_licheerv  
https://github.com/miloserdev/u-boot_sunxi_licheerv  
https://github.com/sehraf/d1-riscv-arch-image-builder  


<br><br>

# Wiki

## [Archriscv](https://archriscv.felixc.at/) rootfs
Default login `root` and password `archriscv`  
> **Warning:** After install you need to **arch-chroot** into new system and install some packages like **networkmanager** and etc.

<br>

## Leds gpio

### Green led onboard
brightness 0-1
```console
echo 1 > /sys/class/leds/green\:status/brightness
```

### SPI RGB led on dock
brightness 0-255  
```console
echo "255" > /sys/class/leds/rgb\:status/brightness
```

R G B 0-255 0-255 0-255  
```console
echo "10 10 10" > /sys/class/leds/rgb\:status/multi_intensity  
```

<br>

## 1.14 inch Display
Show image
```console
fbi -d /dev/fb0 -T 1 -noverbose -a ./riscv.jpg
```

