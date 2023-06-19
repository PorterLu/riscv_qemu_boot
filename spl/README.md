## Introduction
It doesn't work
```
pushd $UBOOT_PATH
export OPENSBI=$OPENSBI_PATH/build/platform/generic/firmware/fw_dynamic.bin
make qemu-riscv64_spl_defconfig
make -j$(nproc)
qemu-system-riscv64 -M virt -smp 4 -m 2G \
-display none -serial stdio \
-bios ./spl/u-boot-spl \
-device loader,file=./u-boot.itb,addr=0x80200000
```
