################################################################################

1. How to Build
	- get Toolchain
		From android git server , codesourcery and etc ..
		 - arm-eabi-4.8
		
	- edit Makefile
		edit "CROSS_COMPILE" to right toolchain path(You downloaded).
		  EX)  export CROSS_COMPILE= $(android platform directory you download)/android/gcc/prebuilts/linux-x86/arm/arm-eabi-4.8/bin/arm-eabi-
       		  Ex)  export CROSS_COMPILE=/usr/local/toolchain/arm-eabi-4.8/bin/arm-eabi-          // check the location of toolchain
		$ export CROSS_COMPILE=(compiler path)
		$ export ARCH=arm
		$ mkdir output
		$ make -C $(pwd) O=output msm8916_sec_defconfig VARIANT_DEFCONFIG=msm8916_sec_j3lte_spr_defconfig SELINUX_DEFCONFIG=selinux_defconfig
		$ make -C $(pwd) O=output 
		$ cp output/arch/arm/boot/zImage arch/arm/boot/zImage

2. Output filesS
	- Kernel : output/arch/arm/boot/zImage
	- module : output/drivers/*/*.ko

3. How to Clean	
		$ cd output
		$ make clean
################################################################################
