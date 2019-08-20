# Maintainer: ckolos (ckolos@gmail.com)
pkgname=glextrusion
pkgver=fb75bf
pkgrel=1
license=('GPL2')
pkgdesc="GL Extrusion libraries and headers"
url="https://github.com/linas/glextrusion"
arch=('x86_64')
provides=('glexutrusion')
makedepends=('make' 'autoconf' 'gcc')
source=('glextrusion::git+https://github.com/linas/glextrusion')
md5sums=('SKIP')

pkgver() {
  cd "$srcdir"/"$pkgname"
  RELEASE=$(git rev-parse refs/remotes/origin/master^{commit})
  echo ${RELEASE:0:6}
}

build() {
  cd "$srcdir"/"$pkgname"
  ./autogen.sh
  ./configure --prefix=/usr --sysconfdir=/etc
  make
}

package() {
  cd "$srcdir"/"$pkgname"
  make DESTDIR="$pkgdir" install
}
