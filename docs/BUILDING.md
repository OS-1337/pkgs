# pkgs
### Packages Repository
## Build Guide
How to make Packages for OS/1337

---
## Requirements
### Basic Build Envoirment
OS/1337 doesn't have any compiler-based dependencies tho as of now only [GCC](https://en.wikipedia.org/wiki/GNU_Compiler_Collection) is documented.
- Please feel free to try [LLVM](https://en.wikipedia.org/wiki/LLVM) and document your findings with an [issue](https://github.com/OS-1337/pkgs/issues/new) or feel free to make a [Pull Request](https://github.com/OS-1337/pkgs/compare).

###
### Dependencies
#### AVOID DEPENDENCY HELL!
OS/1337 intends to be lightweight and packages should do the same.
- If your software depends on anything beyond toybox + musl / linux, then you *must include it* with it!
##### You cannot rely upon any other dependencies nor dependency checking or resolution *at all*!
Otherwise it would baloon the repository's size for no good reason.

###
#### [musl C library](https://musl.libc.org/)
In order to save space as well as avoid bricking userspace, OS/1337 uses [musl](https://en.wikipedia.org/wiki/Musl) as it's [C standard library](https://en.wikipedia.org/wiki/C_standard_library).
- Since we want to keep it simple and safe, we recommend using [the same toolchain as Toybox does](http://landley.net/toybox/downloads/binaries/toolchains/latest/) since that provides us with native and cross-compiling versions of musl to link against, since most build systems will default to [glibc](https://en.wikipedia.org/wiki/Glibc) or whatever standard C-Library said OS/compiler/toolchain uses per default.

###
### Settings
#### Statically linked, single Binaries
In terms of building, it is *required* to make them as static binaries.
- To make this process easier, we recommend [using the musl-cross / musl native library packages as used by Toybox](http://landley.net/toybox/downloads/binaries/toolchains/latest/).

For example, if you want to target [i486 and up](https://en.wikipedia.org/wiki/I486) you want to use the following commands:
````
LDFLAGS=--static CROSS_COMPILE=i486-linux-musl-cross/bin/i486-linux-musl- 
````
- OFC you will need to have the appropriate musl-cross package placed in the same directory.
  - See also the [toybox FAQs regarding cross-compiling](http://landley.net/toybox/faq.html#cross).
- This approach should work on [all architectures supported by Toybox & Linux](http://landley.net/toybox/faq.html#targets).
---

## FAQs
### How can I see if my program actually works?
Test it in a VM i.e. QEMU with OS/1337 in it.
- Your Application will most likely not run at all on your host OS you build it on unless it's identical to the targeted system and you build under OS71337.

###
### My Application doesn't run or crashes or doesn't work as intended!
Calm down and see if you have all the prerequesites and settings correct as per documentation.
- Check if certain functionality depends on driver Support.
  - For example, OS/1337 does not come with Xorg nor Wayland support nor drivers for those.
- You may also find out that you need certain 3rd party libraries to build said software correctly.
  - For example, [toybox's wget implementation needs OpenSSL libraries that are not included in the toybox sources](https://github.com/landley/toybox/issues/451) so you need to add them to it.

If in doubt, ask some developers of said Software if they want to take a closer look.
- If said software is open-source and the developmers aim at both portability and compatibility they'll likely be able and willing to take a closer look at it.


---