## command
```
export USER=...

// s mode uboot
make -C /home/$USER/u-boot/ qemu-riscv64_smode_defconfig
make -C /home/$USER/u-boot/

//we don't need gpu and output to host stdio directly
qemu-system-riscv64 -M virt -smp 4 -m 2G \
-display none -serial stdio \
-kernel /home/$USER/u-boot/u-boot.bin
```
