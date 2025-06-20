##	About [WISHLIST.tsv](WISHLIST.tsv)

###	This file tries to clarify the use-case of the WISHLIST.tsv file.

####	The WISHLIST is intended to note down desired packages.

OFC anyone can build packages for OS/1337 provided they invest the necessary resources to do so.

---

###	Collumns

####	NAME
The name of the package in question. It should be lowercase-only with only ASCIII characters.

####	TAG
This is used as a category-style marker. I.e. `editor` for editors. If a program has multiple functionalities it`s primary one should be listed. If the package is a suite of tools it should be the prime use-case.
The following TAGs are defined:
- `kernel` (Operating System Kernel)
- `userland` (Minimalist core utilities needed besides the kernel)
- `shell` (Shell)
- `development` (Development utilities necessary to build OS/1337 and/or participate in development , including libraries)
- `network` (Tools that are useless without existing network access)
  - `email`	(eMail Clients)
  - `browser` (Web Browsers)
  - `server` (A server that provides a specific service)
    - It must include it's dependencies bundled!
- `filesystem` (Tools for filesystem useage and manipulation)
- `utility` (Other / various utilities that have useage cases)
  - `editor` (Text/Hex/... Editors)
  - `encryption` (Tools for encryption and decryption of messages, files and filesystems)
  - `media` (Media playback/editing programs)
- `other` (any other categoty or uncategorized = default)
  - `config` (A specific configuration/setup for a different package that necessitates it.)
    - It must include said dependent program as part of it. I.e. `NvChad` will install it's own `neovim` and set it up to have it's configuration loaded.

####	GROUP
This is intended to seperate the packages for prioritization and whether or not they are included.
- `core` are the essential packages of the OS/1337 "Core Edition".
- `main` is the recommended set of tools for a full installation. This category also includes the tools necessary to build OS/1337 and it`s packages.
- `extra` includes anything else that doesn`t fit the former categories. These are intended to be explicitly chosen to be installed on a system.

####	LICENSE
The License under which the software is licensed.

####	SOURCES
The link to the sourcecode tree (git)
- if the field is `-` that means there is no sourcecode tree publicly accessible.

####	RELEASES
The page where any sourcecode releases would be published / made available.
- if the field is `-` that means there are no "releases" as in fixed version numbers.

####	ISSUE #
The issue ID that is used to track this package.
- If the ID is `-` then there is no issue opened *yet*.

####	COMMENTS
This is usually a small explainer text for said package.

---

