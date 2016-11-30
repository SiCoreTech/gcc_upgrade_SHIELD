###Upgrading GCC on SHIELD

SHIELD currently has gcc 4.2, here is what we need for the upgrade:

You can find this information at [gcc.gnu.org/install](https://gcc.gnu.org/install/).

####Prerequisites
  - [x] ISO C++98 compiler 
  - [x] C standard library and headers 
```This affects the popular ‘x86_64-unknown-linux-gnu’ platform (among other multilib targets), for which 64-bit (‘x86_64’) and 32-bit (‘i386’) libc headers are usually packaged separately. If you do a build of a native compiler on ‘x86_64-unknown-linux-gnu’, make sure you either have the 32-bit libc developer package properly installed (the exact name of the package depends on your distro) or you must build GCC as a 64-bit only compiler by configuring with the option --disable-multilib. Otherwise, you may encounter an error such as ‘fatal error: gnu/stubs-32.h: No such file```
  - [ ] GNAT ```In order to build the Ada compiler```
  - [ ] A POSIX or SVR4 awk ```unsure if the version of awk from BusyBox will do the job, however it Is POSIX compliant so it should be good```
  - [ ] GNU binutils
  - [x] GNU make version 3.80 or later
  - [ ] GNU tar version 1.14 or later ```unsure if BusyBox version good enough```
  - [ ] Perl version 5.6.1 ```currently not working, may not need for linux/ppc target```
  - [ ] GNU Multiple Precision Library (GMP) version >=4.3.2 ```unsure if version meets requirement, if GMP is already installed but it is not in your library search path, you will have to configure with the --with-gmp configure option. See also --with-gmp-lib and --with-gmp-include.```
  - [ ] MPFR Library version >=2.4.2 ```header does not exist, unsure about library. It can be downloaded from http://www.mpfr.org/. If an MPFR source distribution is found in a subdirectory of your GCC sources named mpfr, it will be built together with GCC. Alternatively, if MPFR is already installed but it is not in your default library search path, the --with-mpfr configure option should be used. See also --with-mpfr-lib and --with-mpfr-include. The in-tree build is only supported with the MPFR version that download_prerequisites installs.``` 
  - [ ] MPC Library version >=0.8.1 ```It can be downloaded from http://www.multiprecision.org/. If an MPC source distribution is found in a subdirectory of your GCC sources named mpc, it will be built together with GCC. Alternatively, if MPC is already installed but it is not in your default library search path, the --with-mpc configure option should be used. See also --with-mpc-lib and --with-mpc-include. The in-tree build is only supported with the MPC version that download_prerequisites installs```
  - [ ] isl Library version 0.16, 0.15, or 0.14 ```Necessary to build GCC with the Graphite loop optimizations. It can be downloaded from ftp://gcc.gnu.org/pub/gcc/infrastructure/. If an isl source distribution is found in a subdirectory of your GCC sources named isl, it will be built together with GCC. Alternatively, the --with-isl configure option should be used if isl is not installed in your default library search path.```

####Downloading the Source

[GCC releases](https://gcc.gnu.org/releases.html).  

```If you also intend to build binutils (either to upgrade an existing installation or for use in place of the corresponding tools of your OS), unpack the binutils distribution either in the same directory or a separate one. In the latter case, add symbolic links to any components of the binutils you intend to build alongside the compiler (bfd, binutils, gas, gprof, ld, opcodes, ...) to the directory containing the GCC sources.

***Likewise the GMP, MPFR and MPC libraries*** can be automatically built together with GCC. You may simply run the contrib/download_prerequisites script in the GCC source directory to set up everything. Otherwise unpack the GMP, MPFR and/or MPC source distributions in the directory containing the GCC sources and rename their directories to gmp, mpfr and mpc, respectively (or use symbolic links with the same name).```
