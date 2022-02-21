# qemu

##   qemu 5.2.0
 
 ```
 qemu-system-riscv64 -version
QEMU emulator version 5.2.0 (v5.2.0-dirty)
Copyright (c) 2003-2020 Fabrice Bellard and the QEMU Project developers
 ```
 
 ```
  qemu-system-riscv64 -M virt -m 512M -smp 2 -bios fw_jump.bin -kernel Image -append "rootwait root=/dev/vda console=ttyS0"  -drive file=rootfs.ext2,format=raw,id=hd0 -device virtio-blk-device,drive=hd0 -netdev user,id=net0,hostfwd=::2222-:22 -device virtio-net-device,netdev=net0 -nographic
 ```
 
 ##  qemu 6.1.0
 
 ```
  ./qemu-system-riscv64 -version
QEMU emulator version 6.1.0
Copyright (c) 2003-2021 Fabrice Bellard and the QEMU Project developers
 ```
 
 ```
 ./qemu-system-riscv64  -M virt -m 512M -smp 2 -bios fw_jump.bin -kernel Image -append "root=/dev/vda"  -drive file=rootfs.ext2,format=raw,id=hd0 -device virtio-blk-device,drive=hd0 -netdev user,id=net0,hostfwd=::2222-:22 -device virtio-net-device,netdev=net0 -nographic
 ```
 
# host os

 ```
 Linux ubuntu 4.15.0-76-generic #86-Ubuntu SMP Fri Jan 17 17:25:58 UTC 2020 aarch64 aarch64 aarch64 GNU/Linux
 ```

# Test1

 ## linux
 
 ```
 # uname -a
Linux buildroot 5.12.3-bdong-dev #1 SMP Fri Feb 18 11:26:58 HKT 2022 riscv64 GNU/Linux
# 
 ```
 ## qemu
 
 ```
 ./qemu-system-riscv64 -version
QEMU emulator version 6.1.0
Copyright (c) 2003-2021 Fabrice Bellard and the QEMU Project developers
 ```
 
 ##  run
 
 ```
 /qemu-system-riscv64 -M virt -m 512M -smp 2 -bios fw_jump.bin.bak  -kernel Image -append "root=/dev/vda  ro console=null"  -drive file=rootfs.ext2,format=raw,id=hd0 -device virtio-blk-device,drive=hd0 -netdev user,id=net0,hostfwd=::2222-:22 -device virtio-net-device,netdev=net0 -nographic   -dtb rtt-riscv64-qemu.dtb
 ```
 
 ## load
 
 ```
 # uname -a
Linux buildroot 5.12.3-bdong-dev #1 SMP Fri Feb 18 11:26:58 HKT 2022 riscv64 GNU/Linux
# cd /
# load_fw-shared rtthread.elf 1
 ```
 ![image](https://github.com/magnate3/openamp_riscv/blob/main/pic/load.png)
 
 ### after load in linux
 ![image](https://github.com/magnate3/openamp_riscv/blob/main/pic/after_load_of_linux.png)
 
  ### after load in shell
 ![image](https://github.com/magnate3/openamp_riscv/blob/main/pic/after_load_of_shell.png)
 