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
            'c47da72ec5a010591226f0de4cb569a1e26188284bbf153bb883060eb9db7acb7b90d21e87d49ff459adafa0ea2a17c0038ab8ff22db3e37fd6d877b9b8d19da')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  mvn package -Dmaven.test.skip=true -Dmaven.repo.local=m2
}

package() {
  install -Dm644 "${srcdir}/${pkgname}-${pkgver}/target/$pkgname-$pkgver.jar" "$pkgdir/usr/share/$pkgname/$pkgname.jar"

  mkdir -p -m755 ${pkgdir}/usr/lib/systemd/system
  install -m644 ${srcdir}/${pkgname}.service ${pkgdir}/usr/lib/systemd/system
}
