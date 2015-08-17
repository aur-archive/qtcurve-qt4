# Maintainer : speps <speps at aur dot archlinux dot org>
# Contributor: xduugu

_name=QtCurve-KDE4
pkgname=qtcurve-qt4
pkgver=1.8.14
pkgrel=2
pkgdesc='A configurable set of widget styles for KDE and Gtk. Qt4-only version.'
arch=('i686' 'x86_64')
url="http://craigd.wikispaces.com/"
license=('GPL')
groups=('qtcurve')
depends=('qt4')
makedepends=('cmake')
source=("${url}file/view/$_name-$pkgver.tar.bz2")
md5sums=('b4d7924806058f39e842ce7ffe47a4f8')

build() {
  cd "$srcdir/$_name-$pkgver"

  [ -d build ] || mkdir build && cd build

  cmake .. -DCMAKE_BUILD_TYPE=Release \
           -DCMAKE_INSTALL_PREFIX=/usr \
           -DQTC_QT_ONLY=true
  make
}

package() {
  cd "$srcdir/$_name-$pkgver/build"
  make DESTDIR="$pkgdir/" install
}
