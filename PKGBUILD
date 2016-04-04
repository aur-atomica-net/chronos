# Maintainer: Jason R. McNeil <jason@jasonrm.net>

pkgname=chronos
pkgver=2.4.0
pkgrel=1
pkgdesc='Fault tolerant job scheduler for Mesos which handles dependencies and ISO8601 based schedules'
arch=('any')
url='http://mesos.github.io/chronos/'
license=('Apache')
depends=('java-runtime')
makedepends=('maven' 'nodejs')
source=("${pkgname}-${pkgver}.tar.gz"::"https://codeload.github.com/mesos/chronos/tar.gz/${pkgver}"
  'chronos.service')
sha512sums=('ece02d0c38b721ceb799e0989b8dc9207909fbfa1929ba065190addd27ad6740cba721d882305b32d8a62e91306a7bd4d235a209a410caad8a29bc08413b896c'
            'bb84d73b337090323e081507412748ca5b29281f57ee429a5c7acd43ccf464621fe5c6821a930434b961904c5e52cabaf568f5cf13a9a261ff8a71d59dec1570')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  mvn package -Dmaven.test.skip=true -Dmaven.repo.local=m2
}

package() {
  install -Dm644 "${srcdir}/${pkgname}-${pkgver}/target/$pkgname-$pkgver.jar" "$pkgdir/usr/share/$pkgname/$pkgname.jar"

  mkdir -p -m755 ${pkgdir}/usr/lib/systemd/system
  install -m644 ${srcdir}/${pkgname}.service ${pkgdir}/usr/lib/systemd/system
}
