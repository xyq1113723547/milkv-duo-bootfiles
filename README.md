# milkv-duo-bootfiles
## fip.bin
This is a firmware which contains FSBL, U-Boot, OpenSBI, and FreeRTOS.  
It's extracted from milkv duo's offical image boot partition.  
https://github.com/milkv-duo/duo-buildroot-sdk/releases/tag/Duo-V1.0.4  


## How to build the firmware from source
Look at the offical SDK for milkv duo: https://github.com/milkv-duo/duo-buildroot-sdk  

```
export MILKV_BOARD=milkv-duo
source milkv/boardconfig-milkv-duo.sh
source build/milkvsetup.sh
defconfig cv1800b_milkv_duo_sd
build_uboot
```
General steps are similar, but the last line here generates only the fip.bin, not the whole system image. 

## reason to put binary here rather than upstream

The U-Boot and OpenSBI are not upstreamed yet, and FSBL and FreeRTOS contain precompiled object files, plus two downstream risc-v toolchains need to be installed. Thus, using any third-party software tools to compile them from source, like yocto, would be hard.
