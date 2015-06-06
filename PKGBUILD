# Maintainer: Jason R. McNeil <jason@jasonrm.net>

pkgname=chronos
pkgver=2.3.4
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
sha512sums=(
  "SKIP"
)

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  mvn package -Dmaven.test.skip=true -Dmaven.repo.local=m2
}

package() {
  install -Dm644 "$pkgname/target/$pkgname-$pkgver.jar" "$pkgdir/usr/share/$pkgname/$pkgname.jar"
}

# vim:set ts=2 sw=2 et:
