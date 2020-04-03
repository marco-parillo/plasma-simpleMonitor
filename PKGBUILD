# Original Maintainer of this PKGBUILD file: Martino Pilia <martino.pilia@gmail.com>; revised by Marco Parillo <maparillo@gmail.com>
_upstream_name=plasma-simpleMonitor
pkgname=plasma5-applets-simplemonitor-map
pkgver=0.6.3
pkgrel=1
pkgdesc="A simple monitor for plasma, completely written in QML and Javascript"
arch=('any')
url="https://store.kde.org/p/1173509/"
license=('GPL')
conflicts=('plasma5-applets-simplemonitor')
depends=('plasma-workspace')
optdepends=()
makedepends=('extra-cmake-modules')
source=(https://github.com/marco-parillo/${_upstream_name}/archive/v${pkgver}.tar.gz)
sha512sums=('6ca4145c0a1d7d93c99d32dae1cf03739f06e08e972e46795add555196319f845fc7ea316ce54f591e3fb18c3b5cf81e7caee7afb5b593ca32bdac7c05b94c1c')

build() {
  cd "$srcdir/$_upstream_name-$pkgver"
  mkdir -p build
  cd build
  cmake .. \
        -DCMAKE_INSTALL_PREFIX="`kf5-config --prefix`" \
        -DCMAKE_BUILD_TYPE=Release
  make
}

package() {
  cd "$srcdir/$_upstream_name-$pkgver/build"
  make install DESTDIR="${pkgdir}"
}
