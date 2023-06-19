## Introduction
```
make -C $OPENSBI_PATH/ PLATFORM=generic FW_PAYLOAD_PATH=$UBOOT_PATH/u-boot.bin
qemu-system-riscv64 -M virt -m 256M -nographic -bios $OPENSBI_PATH/build/platform/generic/firmware/fw_payload.elf

qemu-system-riscv64 -M virt -m 256M -m 256M -nographic \
-bios $OPENSBI_PATH/build/platform/generic/firmware/fw_jump.bin \
-kernel $LINUX_PATH/arch/riscv/Image \
-drive file=$ROOTFS_PATH/rootfs.img \
-device virtio-blk-device,drive=hd0 \
-append "root=/dev/vda rw console=ttyS0"
```
