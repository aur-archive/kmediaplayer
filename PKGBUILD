# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kmediaplayer
pkgver=4.99.0
pkgrel=1
pkgdesc='KMediaPlayer'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/kmediaplayer'
license=('LGPL')
depends=('kparts')
makedepends=('extra-cmake-modules')
groups=('kf5-aids')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/portingAids/${pkgname}-${pkgver}.tar.xz")
md5sums=('c97226816eda2bb9294e02ed3816df66')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
