# $Id$
# Contributor: TheKit <nekit1000 at gmail.com>
# Contributor: Bart Ribbers <bribbers@disroot.org>
# Contributor: Alexey Andreyev <aa13q@ya.ru>
# Contributor: Chupligin Sergey <neochapay@gmail.com>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

pkgname=qt6-quickcontrols-nemo
pkgver=6.2.6

pkgrel=1
pkgdesc="Nemomobile Qt Quick Controls"
arch=('x86_64' 'aarch64')
url="https://github.com/nemomobile-ux/qtquickcontrols-nemo"
license=('LGPL-2.1-only AND Apache-2.0')
depends=(
    'qt6-shadertools'
    'qt6-declarative'
    'nemo-theme-default'
    'qt6-svg'
    'google-opensans-fonts'
    'mlite6>=0.5.3'
)
makedepends=('cmake')
source=("${url}/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('98be790f388964469a8d0fb66d591c69ee8a1bae1a0b222b5aa9231d08196054')

build() {
    cd "qtquickcontrols-nemo-${pkgver}"
    cmake \
        -DBUILD_EXAMPLES=OFF \
        -DBUILD_CONTROLS=ON \
        -DCMAKE_INSTALL_PREFIX:PATH='/usr'
    make all
}

package() {
    cd "qtquickcontrols-nemo-${pkgver}"
    make DESTDIR="$pkgdir" install
}
