[![Build Status](https://travis-ci.org/vtorri/etui.svg?branch=master)](https://travis-ci.org/vtorri/etui)<a href="https://scan.coverity.com/projects/vtorri-etui">
  <img alt="Coverity Scan Build Status"
       src="https://scan.coverity.com/projects/13637/badge.svg"/>
</a>

### Étui 
##### A Multiple Document Library and Viewer

### License:

This library is released under the GPL v3 license

### Library:

 **Requirements** :
 
  - Evil (on Windows)
  - Eina
  - Eet
  - Ecore
  - Evas
  - Eio

### Binary:

 **Requirements**:
  - Evil (Windows)
  - Eina
  - Eet
  - Evas
  - Ecore
  - Ecore_Input
  - Elementary

### Supported backends (actual and planned):

- [x] **PDF** and **XPS**, Requires *zlib, freetype2, libopenjp2, muPDF 1.11*.
- [x] **COMIC BOOK** (cbz, cbr, cb7, cbt, cba), Requires *libarchive*.
- [x] **DjVu**: Requires *libdjvu (DjVuLibre)*
- [x] **TIFF**, Requires *libtiff*.
- [ ] **Postscript**
	- ***Requirements***: *libgs*
	- ***compilation***: *make so (debug mode: make sodebug)*
	- ***installation***: *make soinstall (debug mode: make sodebuginstall)*
- [ ] **DVI**: Requires *libdvi*
- [ ] **EPUB**: Requires *libarchive*
- [ ] **CHM**: Requires *libarchive*

### Compilation:

Common usage of configure (created by autogen.sh). Here are some example to compile with PDF and DJVU support:

- **Windows** (MinGW 32bits):
```
./configure --host=i686-w64-mingw32 --disable-static --enable-gpl --with-mupdf-includedir=/home/vtorri/tmp/mupdf-1.11-source/include --with-mupdf-static-libs="-Wl,/home/vtorri/tmp/mupdf-1.11-source/build/release/libmupdf.a -Wl,/home/vtorri/tmp/mupdf-1.11-source/build/release/libmupdfthird.a
```


- **Windows** (MinGW 64bits):
```
./configure --host=x86_64-w64-mingw32 --disable-static --enable-gpl --with-mupdf-includedir=/home/vtorri/tmp/mupdf-1.11-source/include --with-mupdf-static-libs="-Wl,/home/vtorri/tmp/mupdf-1.11-source/build/release/libmupdf.a -Wl,/home/vtorri/tmp/mupdf-1.11-source/build/release/libmupdfthird.a
```

- **Fedora**:
```
./configure --enable-gpl --with-mupdf-static-libs=-Wl,/usr/lib64/libmupdf.a --with-mupdf-shared-libs="-ljbig2dec
```
- **ArchLinux**: *See pkgbuild/PKGBUILD*

- **Gentoo**:
```
./configure --enable-gpl --with-mupdf-shared-libs="-lmupdf"
```

- **OpenBSD** or **FreeBsd**:
```
./configure --enable-gpl --with-mupdf-includedir=-I/usr/local/include --with-mupdf-shared-libs="-L/usr/local/lib -lmupdf -lmupdfthird"
```

### Key bindings: ([C] means can be configureey bindings: ([C] means can be configured)

- Ctrl-q : quit
- Ctrl-o : open file
- [C] F1: help
- [C] right arrow or space : next page
- [C] left arrow or backspace : previous page
- [C] page up : page + 10
- [C] page down : page - 10
- [C] F11: toggle fullscreen esc : exit fullscreen
- [C] Ctrl-+ : scale * sqrt(2)
- [C] Ctrl-- : scale / sqrt(2)
- [C] Ctrl-0 : zoom to fit height (not done yet)
- [C] Ctrl-1 : zoom to original size
- [C] Ctrl-2 : zoom to fit width (not done yet)
- [C] Ctrl-home : go to first page
- [C] Ctrl-end : go to last page

Mouse bindings:
---------------

- double left click : toggle fullscreen
- Ctrl-wheel up : scale * sqrt(2)
- Ctrl-wheel down : scale / sqrt(2)
