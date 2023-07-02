AUR Packages
============

Packages I own or maintain or that I modified/fixed for my usage.

Repository
----------

I will generally publish built versions (not guaranteed) to my public pacman repository.

Import my PGP key:
```sh
$ sudo pacman-key --recv A879430AF260A189
$ sudo pacman-key --lsign a879430af260a189
```

Add to your `pacman.conf`:
```
[archwill]
Server = https://repo.archwill.net/archlinux/$repo/os/$arch
SigLevel = Required DatabaseOptional
```
