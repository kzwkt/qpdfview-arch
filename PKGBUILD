# Maintainer: Carlos Aznarán <caznaranl@uni.pe>
# Contributor: Antonio Rojas <arojas@archlinux.org>
# Contributor: Alad Wenter <alad@mailbox.org>
# Contributor: Adam Reichold <adam.reichold@t-online.de>
pkgname=qpdfview
pkgver=0.5.0
pkgrel=3
pkgdesc="A tabbed PDF viewer using the poppler library"
url="https://launchpad.net/${pkgname}"
arch=(x86_64)
license=(GPL-2.0-or-later)
depends=(libcups libsynctex poppler-qt6 qt6-svg)
makedepends=(qt6-tools libspectre djvulibre)
optdepends=('libspectre: for PostScript support'
  'djvulibre: for DjVu support')
source=(${url}/trunk/${pkgver}/+download/${pkgname}-${pkgver::-2}.tar.gz{,.asc})

build() {
  cd ${pkgname}-${pkgver::-2}
  export QMAKE_CXXFLAGS_RELEASE="-O2 -g0 -DNDEBUG"
  qmake6 qpdfview.pro
  make
}

package() {
  cd ${pkgname}-${pkgver::-2}
  make INSTALL_ROOT="$pkgdir" install
}
