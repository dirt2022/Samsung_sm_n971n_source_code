# Samsung_sm_n971n_source_code
It is broken!! It packed whth android NDK r17c,samsung N971N source code,and debian_chroot_environment(base)
causes the network is slow so I will fork a lot of repos.
VERSION:N971N , ANDROID 12, N971NKSU2GULF .
# HOW to use?
run these commands on your tty
_____
"apt install chroot debootstrap -y"  &&
"debootstrap --arch=amd64 bullseye ./rootfs" &&
sudo mount --rbind /dev ./rootfs/dev &&
sudo mount --rbind /proc ./rootfs/proc &&
sudo mount --rbind /sys ./rootfs/sys &&
sudo chroot ./rootfs &&
apt update &&
apt install build-essential bc bison binutils git -y &&
git clone https://github.com/dirt2022/Samsung_sm_n971n_source_code/ ./work &&
mkdir tools &&
wget https://dl.google.com/android/repository/android-ndk-r17c-linux-x86_64.zip &&
mv android-ndk-r17c-linux-x86_64.zip ./tools &&
cd tools &&
unzip android-ndk-r17c-linux-x86_64.zip && rm android-ndk-r17c-linux-x86_64.zip &&
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
