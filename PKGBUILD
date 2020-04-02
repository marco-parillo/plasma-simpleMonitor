# Original Maintainer of this PKGBUILD file: Martino Pilia <martino.pilia@gmail.com>; revised by Marco Parillo <maparillo@gmail.com>
_upstream_name=plasma-simpleMonitor
pkgname=plasma5-applets-simplemonitor-map
pkgver=0.6.2
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
sha512sums=('7f8f62488e7de1aa5efc3184a6394297f075fb98157b670e0552a3c21377e189e551bfee02141e3fa810dc00e586bdff9cd00818e69d435693f7f9b86cda4a0e')

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
