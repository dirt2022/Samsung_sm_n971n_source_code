# Samsung_sm_n971n_source_code
It is broken!! It packed whth android NDK r17c,samsung N971N source code,and debian_chroot_environment(base)
# HOW to use?
run 'apt install chroot' in your tty,then input 'mount --rbind /dev $path_to_this_DIR/dev' 'mount --rbind /proc $path_to_this_dir/proc' 'mount --rbind /sys $path_th_this_DIR/sys'
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
