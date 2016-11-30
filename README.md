###Upgrading GCC on SHIELD

SHIELD currently has gcc 4.2, here is what we need for the upgrade:

You can find this information at [gcc.gnu.org/install](https://gcc.gnu.org/install/).

1. Prerequisites
  - [x] ISO C++98 compiler 
  - [x] C standard library and headers 
```This affects the popular ‘x86_64-unknown-linux-gnu’ platform (among other multilib targets), for which 64-bit (‘x86_64’) and 32-bit (‘i386’) libc headers are usually packaged separately. If you do a build of a native compiler on ‘x86_64-unknown-linux-gnu’, make sure you either have the 32-bit libc developer package properly installed (the exact name of the package depends on your distro) or you must build GCC as a 64-bit only compiler by configuring with the option --disable-multilib. Otherwise, you may encounter an error such as ‘fatal error: gnu/stubs-32.h: No such file```
