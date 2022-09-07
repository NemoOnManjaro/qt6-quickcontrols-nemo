# $Id$
# Contributor: TheKit <nekit1000 at gmail.com>
# Contributor: Bart Ribbers <bribbers@disroot.org>
# Contributor: Alexey Andreyev <aa13q@ya.ru>
# Contributor: Chupligin Sergey <neochapay@gmail.com>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

pkgname=qt5-quickcontrols-nemo
pkgver=5.7.4

pkgrel=1
pkgdesc="Nemomobile Qt Quick Controls"
arch=('x86_64' 'aarch64')
url="https://github.com/nemomobile-ux/qtquickcontrols-nemo"
license=('LGPL-2.1-only AND Apache-2.0')
depends=('qt5-quickcontrols' 'nemo-theme-default' 'qt5-svg' 'google-opensans-fonts' 'maliit-nemo-keyboard' 'mlite')
makedepends=('cmake')
source=("${url}/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('ff0609ae1de3a97fe5970cedc0974537e952d9bb787a8ddc3adf0f618b333397')

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
