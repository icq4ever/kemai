# Maintainer: Matthias De Bie <mattydebie@gmail.com>

pkgname="kemai"
pkgdesc="A QT5 client for kimai2"
pkgver="0.10.0"
pkgrel=1
url="https://github.com/AlexandrePTJ/kemai"
arch=('i686' 'x86_64')
license=('MIT')
source=("https://github.com/AlexandrePTJ/kemai/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('2b77fcc915f2bdc6012d43cd65570363e2ca7ba38a424fe1242b1cfc3655f1eb')
makedepends=("cmake")
depends=("qt5-base")

build() {
  cd kemai-${pkgver}
  cmake . -B build -DCMAKE_BUILD_TYPE=Release
  cmake --build build --config Release
}

package() {
  mkdir ${pkgdir}/usr/bin -p
  mkdir ${pkgdir}/usr/share/applications -p
  cp -f kemai-${pkgver}/build/src/Kemai ${pkgdir}/usr/bin/
  cp -f kemai-${pkgver}/bundle/linux/sysroot/usr/bin/kemai-wrapper.sh ${pkgdir}/usr/bin/
  cp -f kemai-${pkgver}/bundle/linux/sysroot/kemai-wrapper.desktop ${pkgdir}/usr/share/applications/kemai.desktop
}
