# pkgs
### Packages Repository
This is the official repository for OS/1337-specific Applications.

Packages are being installed, uninstalled and updated using [spm](https://github.com/OS-1337/spm), the [Package Manager](https://en.wikipedia.org/wiki/Package_manager) for [OS/1337](https://github.com/OS-1337/OS1337).

---
## Packages
### Supported Architectures

###
#### [amd64](./bin/amd64)
For 64bit AMD64-compatible Systems
- [List of Packages](./bin/amd64/index.tsv)
###
#### [ix86](./bin/ix86)
For 32bit i386-compatible Systems
- [List of Packages](./bin/ix64/index.tsv)
###
#### [arm11v5](./bin/arm11v5)
This includes low-end 32bit ARM-based SBCs like The Raspberry Pi Zero
- [List of Packages](./bin/arm11v5/index.tsv)
##

These are the currently planned ones, but more can be added anytime.

---
## FAQs
### How To Contribute?
#### Just start...
Whilst this is a young project, there is a lot of space to form stuff.

If your package is something useful or something that adds value to the vision of a lightweight and flexible, embedded-capable CLI & TUI Linux Desktop, then it'll likely be added in.
- Feel free to open up a pull request / issue anytime.
#### We track all the wishes in the [wishlist in this project, so please see if your wish is already on it](docs/WISHLIST.tsv). 

###
### How are packages build?
We are working on a detailed [build guide](docs/BUILDING.md) as part of the [Documentation](docs) as we develop and finalize the specs.
#### TL;DR: To increase portability all packages are statically linked with their dependencies!
OS/1337 uses [musl](https://en.wikipedia.org/wiki/Musl) and in specific uses [the same musl-cross toolchain](https://landley.net/toybox/downloads/binaries/toolchains/latest/) as [being used to cross compile toybox static binaries](http://landley.net/toybox/faq.html#cross) since [toybox](https://landley.net/toybox/) is being used as it's [Userspace](https://en.wikipedia.org/wiki/User_space_and_kernel_space).

###
### Licenses?
#### TL;DR: Don't be a dick!
##### As a reference repository for [OS/1337](https://github.com/OS-1337/OS1337) we want to focus on [FLOSS](https://en.wikipedia.org/wiki/Free_and_open-source_software)-licensed software.
We do believe in the freedom of authors to choose their license as they see fit, but we also believe that we don't want stuff that makes this distro another [Minix](https://en.wikipedia.org/wiki/Minix#Licensing) due to licensing conflicts..
##### The following licenses thus are not permissible for Software in this repo.
- Any License that restricts the use, sharing and transfer or reuse of OS/1337, including but not limited to:
  - CCSS of any kind
    - Also known as: [Commercial](https://en.wikipedia.org/wiki/Commercial_software) and/or [Closed-Source](https://en.wikipedia.org/wiki/Proprietary_software) Software.
  - Licenses that completely disregard the legal facts and laws in regards to software licensing and patents, like:
    - [AGPL (v3)](https://en.wikipedia.org/wiki/GNU_Affero_General_Public_License)
  - "Anti-Free Licenses" that basically act as a leverage to prevent competitors from offering a better service or product and thus are cleary violating the [OSI's Open Source Definition](https://en.wikipedia.org/wiki/The_Open_Source_Definition).
    - Espechally [SSPL](https://en.wikipedia.org/wiki/Server_Side_Public_License) and other "Source Available" - Licenses which don't allow much beyond "compile it yourself for your system" and/or "[non-commercial] self-hosting".
####
##### Furthermore we don't want to support or be complicit in [Enshittification](https://en.wikipedia.org/wiki/Enshittification) so we won't allow bloated & single-use applications that have [Vendor Lock-In](https://en.wikipedia.org/wiki/Vendor_lock-in) or "[Provider Lock-In](https://en.wikipedia.org/wiki/SIM_lock)" of any kind.
So please understand that we won't support like [Signal](https://en.wikipedia.org/wiki/Signal_(software)) or [Discord](https://en.wikipedia.org/wiki/Discord) clients, but would allow CLI/TUI-based Clients for [XMPP](https://profanity-im.github.io/) or [Zulip](https://github.com/zulip/zulip-terminal).
- But feel free to build those clients yourself and host them yourself.

###
#### These rules may be changed and if necessary as few as possible exceptions will be allowed - if any.
Granted, don't expect us to do so...
##

### Other Repos?
#### Please refer to [spm](https://github.com/OS-1337/spm) as the [Package Manager](https://en.wikipedia.org/wiki/Package_manager), since this is the main repository for OS/1337.
OFC nothing prevents one from building one's own repository.

---
## FAQs

###
### I want to submit an application to this repo!
#### That's nice!
Please [open up a new issue](http://github.com/OS-1337/pkgs/issues/new) or a [Pull request](https://github.com/OS-1337/pkgs/pulls) for the package as per [WISHLIST](docs/WISHLIST.tsv).

###
### My submission got rejected!
#### Thats sad to hear, but please don't despair!
Unless it's a duplicate submission you'll likely get a detailed response why your request was denied.
##### The following reasons may be the most likely why a submission got rejected.
####
- Non-Free Software
  - Just because something has *"Source Available"* doesn't mean it's *"Open Source"*!
    - A good example is [Tarsnap](https://www.tarsnap.com) which only has [published Sourcecode](https://www.tarsnap.com/open-source.html).
  - Single-Vendor / Single-Provider Lock-Ins.
    - Again: Tarsnap would fit that since it's only useable with the Tarsnap Service and doesn't allow self-hosting or even switching providers at all.
####
- Duplicate Submission
  - Please [search the issues before submitting!](https://github.com/OS-1337/pkgs/issues)
    - Retries are only permitted if the issues for denying it were alleviated.
      - Please provide source material for easy checking!

###
### I want an application on the [Wishlist](docs/WISHLIST.tsv) to be available now!
#### Feel free to contribute!
##### Please read the [build guide on how to compile an application for OS/1337](docs/BUILDING.md).
If you have done that, you may work towards building said packages and creating a bash script to automate this in a reproducible manner.
- We recommend to default with a matching musl-cross library even when targeting your native hardware & architecture!

Once you get reproduceable results and working binaries and configs, please feel free to document the exact steps and open up an issue detailing it.
