# AKlab4


## Commands for export:

```
export ARCH=arm
```
```
export PATH=/opt/gcc-arm-10.3-2021.07-x86_64-arm-none-eabi/bin:$PATH

```
```
export CROSS_COMPILE='ccache arm-none-eabi-'

```
```
export KDIR=$HOME/repos/linux-stable
```

## Commands for rebuild archive:

```
cd ~/repos/busybox/_install
```
```
find . | cpio -o -H newc | gzip > ../rootfs.cpio.gz
```
```
cd ..
```

## Commands for start QEMU:

```
qemu-system-arm -kernel _install/boot/zImage -initrd rootfs.cpio.gz -machine virt -nographic -m 512 --append "root=/dev/ram0 rw console=ttyAMA0,115200 mem=512M"
```

## Commands for check:

```
insmod hello1.ko
```
```
insmod hello2.ko hello=кількість повторів
```
```
modinfo hello1.ko
```
```
modinfo hello2.ko
```
```
rmmod hello2
```
```
rmmod hello1
```
## Commands for some control:

```
cat /sys/module/hello2/parameters/hello
```

