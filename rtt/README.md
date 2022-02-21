
# solve bugs
## 1)bsp/qemu-riscv-virt64/driver/drv_uart.h

```
#define UART0_BASE            (0x10000000L)
#define UART1_BASE            (0x10002000L)
#define UART_BASE             UART0_BASE // not UART1_BASE
```

# compile
## opensbi
[opensbi for qemu](https://github.com/magnate3/opensbi_qemu)
```
 make PLATFORM=qemu/virt CROSS_COMPILE=riscv64-linux-gnu-
```
# rtthread compile

## patches
 ![image](https://github.com/magnate3/openamp_riscv/blob/main/pic/rt_patch.png)
 
 
```
bsp/qemu-riscv-virt64
export RTT_EXEC_PATH=/usr/bin
scons -c
scons --menuconfig
scons
```

# run


```
qemu-system-riscv64 -nographic -machine virt -m 256M -kernel rtthread.elf -bios fw_jump.elf 

OpenSBI v0.5-52-g30cdf00
   ____                    _____ ____ _____
  / __ \                  / ____|  _ \_   _|
 | |  | |_ __   ___ _ __ | (___ | |_) || |
 | |  | | '_ \ / _ \ '_ \ \___ \|  _ < | |
 | |__| | |_) |  __/ | | |____) | |_) || |_
  \____/| .__/ \___|_| |_|_____/|____/_____|
        | |
        |_|

Platform Name          : QEMU Virt Machine
Platform HART Features : RV64ACDFIMSU
Platform Max HARTs     : 8
Current Hart           : 0
Firmware Base          : 0x80000000
Firmware Size          : 120 KB
Runtime SBI Version    : 0.2

PMP0: 0x0000000080000000-0x000000008001ffff (A)
PMP1: 0x0000000000000000-0xffffffffffffffff (A,R,W,X)
heap: [0x802356b9 - 0x866356b9]

 \ | /
- RT -     Thread Operating System
 / | \     4.0.4 build Feb 21 2022
 2006 - 2021 Copyright by rt-thread team
Hello RISC-V!
msh />
```

## run for openamp

```

```


 