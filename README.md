# hft-server-settings

Collection of tidbits for HFT server config.

## Disable Hyperthreading (Bios)

Use `lscpu` to determine how many threads are listed / core.

```
$ lscpu
Architecture:          x86_64
CPU op-mode(s):        32-bit, 64-bit
Byte Order:            Little Endian
CPU(s):                32
On-line CPU(s) list:   0-31
Thread(s) per core:    2                    // <---------- This should be 1
Core(s) per socket:    8
Socket(s):             2
NUMA node(s):          4
Vendor ID:             AuthenticAMD
CPU family:            21
Model:                 1
Model name:            AMD Opteron(tm) Processor 6282 SE
Stepping:              2
CPU MHz:               2600.058
BogoMIPS:              5200.11
Virtualization:        AMD-V
L1d cache:             16K
L1i cache:             64K
L2 cache:              2048K
L3 cache:              6144K
NUMA node0 CPU(s):     0,2,4,6,8,10,12,14
NUMA node1 CPU(s):     16,18,20,22,24,26,28,30
NUMA node2 CPU(s):     1,3,5,7,9,11,13,15
NUMA node3 CPU(s):     17,19,21,23,25,27,29,31
Flags:                 fpu vme de pse tsc msr pae mc
```

## Disable Power Savings Mode (Bios)

## Remove cpus from kernel scheduler

Use the `isolcpu` command to dedicate just two CPUs to the kernel. The remaining can be used for userspace trading processes.

https://www.linuxtopia.org/online_books/linux_kernel/kernel_configuration/re46.html

## Resources

https://access.redhat.com/sites/default/files/attachments/201501-perf-brief-low-latency-tuning-rhel7-v1.1.pdf
