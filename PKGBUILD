# $Id$
# Contributor: TheKit <nekit1000 at gmail.com>
# Contributor: Bart Ribbers <bribbers@disroot.org>
# Contributor: Alexey Andreyev <aa13q@ya.ru>
# Contributor: Chupligin Sergey <neochapay@gmail.com>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

pkgname=qt5-quickcontrols-nemo
pkgver=5.7.6

pkgrel=1
pkgdesc="Nemomobile Qt Quick Controls"
arch=('x86_64' 'aarch64')
url="https://github.com/nemomobile-ux/qtquickcontrols-nemo"
license=('LGPL-2.1-only AND Apache-2.0')
depends=(
    'qt5-quickcontrols'
    'nemo-theme-default'
    'qt5-svg'
    'google-opensans-fonts'
    'mlite'
)
makedepends=('cmake')
source=("${url}/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('404583ebaf84fcb19e70c3c51ba0c487e6fbb81e35f3f41943d64d64178e9757')

build() {
    cd "qtquickcontrols-nemo-${pkgver}"
    cmake \
        -DBUILD_EXAMPLES=OFF -DBUILD_CONTROLS=ON \
        -DCMAKE_INSTALL_PREFIX:PATH='/usr'
    make all
}

package() {
    cd "qtquickcontrols-nemo-${pkgver}"
    make DESTDIR="$pkgdir" install
}
