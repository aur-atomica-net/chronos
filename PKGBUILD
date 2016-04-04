# Maintainer: Jason R. McNeil <jason@jasonrm.net>

pkgname=chronos
pkgver=2.4.0
pkgrel=1
pkgdesc='Fault tolerant job scheduler for Mesos which handles dependencies and ISO8601 based schedules'
arch=('any')
url='http://mesos.github.io/chronos/'
license=('Apache')
depends=('java-runtime' 'nodejs')
makedepends=('maven')
source=(
  "${pkgname}-${pkgver}.tar.gz"::"https://codeload.github.com/mesos/chronos/tar.gz/${pkgver}"
)
sha512sums=('ece02d0c38b721ceb799e0989b8dc9207909fbfa1929ba065190addd27ad6740cba721d882305b32d8a62e91306a7bd4d235a209a410caad8a29bc08413b896c')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  mvn package -Dmaven.test.skip=true -Dmaven.repo.local=m2
}

package() {
  install -Dm644 "${srcdir}/${pkgname}-${pkgver}/target/$pkgname-$pkgver.jar" "$pkgdir/usr/share/$pkgname/$pkgname.jar"
}

# vim:set ts=2 sw=2 et:
