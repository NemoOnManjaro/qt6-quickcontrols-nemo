# $Id$
# Contributor: TheKit <nekit1000 at gmail.com>
# Contributor: Bart Ribbers <bribbers@disroot.org>
# Contributor: Alexey Andreyev <aa13q@ya.ru>
# Contributor: Chupligin Sergey <neochapay@gmail.com>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

pkgname=qt5-quickcontrols-nemo
pkgver=5.7.5

pkgrel=1
pkgdesc="Nemomobile Qt Quick Controls"
arch=('x86_64' 'aarch64')
url="https://github.com/nemomobile-ux/qtquickcontrols-nemo"
license=('LGPL-2.1-only AND Apache-2.0')
depends=('qt5-quickcontrols' 'nemo-theme-default' 'qt5-svg' 'google-opensans-fonts' 'maliit-nemo-keyboard' 'mlite')
makedepends=('cmake')
source=("${url}/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('a4da7dfc0238aa2ef50f7a6454ec116785671dec48b956c7cb60e3c91012faae')

prepare() {
    # TODO: upstream building examples optional
    # https://t.me/NemoMobile/17555
    cd qtquickcontrols-nemo-$pkgver
    sed -i.bak 's/add_subdirectory[(]examples[)]//' CMakeLists.txt
}

build() {
    cd "qtquickcontrols-nemo-${pkgver}"
    cmake \
        -DCMAKE_INSTALL_PREFIX:PATH='/usr'
    make all
}

package() {
    cd "qtquickcontrols-nemo-${pkgver}"
    make DESTDIR="$pkgdir" install
}
