# how-to-package-deb
A tutorial for making a .deb package

1. Compile your app
```
$ g++ app.cpp -o app
```
2. Create package directory structure
```
$ mkdir mypackage
$ mkdir mypackage/DEBIAN
$ touch mypackage/DEBIAN/control
```
3. Configure deb control file
```
Package: packagename
Version: 0.1
Section: custom
Priority: optional
Architecture: amd64
Essential: no
Maintainer: example@mail.com
Description: Description for your package
```
4. Move executable to the correct directory
```
$ mkdir -p mypackage/usr/bin
$ mv app mypackage/usr/bin
```
5. Build package 
```
$ dpkg-deb --build mypackage
```