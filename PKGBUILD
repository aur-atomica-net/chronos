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
sha512sums=("7500e58479e461d01f1c303729c34a6180cfaa130c4f15d6f02f2e612b4816900ec3b63b5067883e829bce5afb89e8b7ff2cec5898d8512139954b3bb98858b5")

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  mvn package -Dmaven.test.skip=true -Dmaven.repo.local=m2
}

package() {
  install -Dm644 "${srcdir}/${pkgname}-${pkgver}/target/$pkgname-$pkgver.jar" "$pkgdir/usr/share/$pkgname/$pkgname.jar"
}

# vim:set ts=2 sw=2 et:
