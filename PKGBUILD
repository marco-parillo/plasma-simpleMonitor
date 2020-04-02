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
sha512sums=('f3f56e1747c014ebdec1f6c09c250c51a6cb598e17f78450c2b787009e4ccbdc4838449e2cc7ae6d95621a8cc9f01bdcc1725c662c098fa7b72a9ae879830027')

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
