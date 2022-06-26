# Samsung_sm_n971n_source_code
It is broken!! It packed whth android NDK r17c,samsung N971N source code,and debian_chroot_environment(base)
causes the network is slow so I will fork a lot of repos.
# HOW to use?
run these commands
___
"apt install chroot debootstrap -y"
___
"debootstrap --arch=amd64 bullseye ./rootfs"
___
sudo mount --rbind /dev ./rootfs/dev
___
sudo mount --rbind /proc ./rootfs/proc
__
sudo mount --rbind /sys ./rootfs/sys
___
sudo chroot ./rootfs
___
apt update
___
apt install build-essential bc bison binutils git -y
___
git clone https://github.com/dirt2022/Samsung_sm_n971n_source_code/ ./work
___
mkdir tools
___
wget https://dl.google.com/android/repository/android-ndk-r17c-linux-x86_64.zip
___
mv android-ndk-r17c-linux-x86_64.zip ./tools
___
cd tools
___
unzip android-ndk-r17c-linux-x86_64.zip && rm android-ndk-r17c-linux-x86_64.zip
___
# BUGS
/*
 ^
arch/arm64/kernel/vdso/gettimeofday.S:1:0: error: unknown feature modifier 'lse'

________
 /*
 ^
arch/arm64/kernel/vdso/sigreturn.S:1:0: error: unknown feature modifier 'lse'
________

 /*
 ^

//the config file is preconfig by me. but When I change dir to the 'work_dir' and try to make samsung_n971n_kernel It does not work.
"

# How to build
lunch these commands
__
chroot ./rootfs && make -j3 (you also can run make menuconfig,the config file is already in .config,so you don't have to run ./configure;but install libncurses-dev first )
