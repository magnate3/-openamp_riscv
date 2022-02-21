# fw_jump.elf
fw_jump.elf is for test rtt in s-mode

```
 qemu-system-riscv64 -nographic -machine virt -m 256M -kernel rtthread.elf -bios fw_jump.elf
```
 
 