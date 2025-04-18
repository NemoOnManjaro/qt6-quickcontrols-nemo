# $Id$
# Contributor: TheKit <nekit1000 at gmail.com>
# Contributor: Bart Ribbers <bribbers@disroot.org>
# Contributor: Alexey Andreyev <aa13q@ya.ru>
# Contributor: Chupligin Sergey <neochapay@gmail.com>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

pkgname=qt6-quickcontrols-nemo
pkgver=6.2.4

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
sha256sums=('0cd79263e2ee1fac171fd0469a24d5a2c2fdf0281eabfde673573a5c223ae388')

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
