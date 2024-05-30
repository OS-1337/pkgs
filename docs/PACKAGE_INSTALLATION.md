# pkgs
Packages Repository
##	Package Installation
###	How to Install packages

###	1. Using spm:
####	NOTE: This requires spm to be installed and configured!
[spm](https://github.com/OS-1337/spm) is the main package manager for OS/1337 and is designed to make installing and removing packages easy.

- To install a package named```demo.app```, run ```spm install demo.app```.
- To uninstall a package named```demo.app```, run ```spm remove demo.app```.

#####	Per default, ```spm``` will install all applications globally in their subdirectories under ```/bin/```.
For Example ```demo.app``` will be installed under ```/bin/demo.app/```. 

- It will contain every dependency for said application besides the running ```toybox + musl / linux``` system aka. [OS/1337](https://os1337.com).

#####	If you do not want to install said application globally, it is recommended to manually install it $HOMEDIR/.apps/ of the user that should run it.



###	2. manual installation
####	NOTE: This is disrecommended as it prevents ```spm``` from updating and managing application installations.

To install an application manually into the system, you need to [add it's $PATH permanently to the system](https://www.digitalocean.com/community/tutorials/how-to-view-and-update-the-linux-path-environment-variable#step-3-mdash-permanently-adding-a-directory-to-the-path-variable) beforehand.
- You may then install said application either globally into it's subdirectory under ```/bin/``` or you may install it per user under their ```$HOMEDIR/.apps/``` under ```/home/$USERNAME/.apps/```.

For uninstallation, simply remove it's ```$PATH``` variable and delete the directory for said application.
