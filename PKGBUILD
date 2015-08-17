# Maintainer: Arch Haskell Team <arch-haskell@haskell.org>
# Contributor: Arch Haskell Team <arch-haskell@haskell.org>

_hkgname=threadscope
pkgname=threadscope
pkgver=0.2.2
pkgrel=1
pkgdesc="A graphical thread profiler."
url="http://hackage.haskell.org/package/${_hkgname}"
license=('custom:BSD3')
arch=('i686' 'x86_64')
makedepends=('ghc' 'haskell-array' 'haskell-binary' 'haskell-cairo'
             'haskell-containers' 'haskell-filepath' 'haskell-ghc-events'
             'haskell-gtk' 'haskell-mtl' 'haskell-unix' 'haskell-pango'
             'haskell-time' 'haskell-deepseq')
depends=('gmp')
options=('strip')
source=(http://hackage.haskell.org/packages/archive/${_hkgname}/${pkgver}/${_hkgname}-${pkgver}.tar.gz)
md5sums=('f42ff14c8e16dd269de4bcc43f43a31f')

build() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup configure --prefix=/usr --docdir=/usr/share/doc/${pkgname} -O
    runhaskell Setup build
}

package() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup copy --destdir=${pkgdir}
    install -D -m644 LICENSE ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
    rm -f ${pkgdir}/usr/share/doc/${pkgname}/LICENSE
}
