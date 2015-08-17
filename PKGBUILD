# Contributor: Andreas Baumann <abaumann at yahoo dot com>

pkgname=snowball-c
pkgver=20140401
pkgrel=1
pkgdesc="Snowball rule-based stemming algorithms (shared lib + stemwords executable)"
arch=('i686' 'x86_64')
url='http://snowball.tartarus.org/'
license=('BSD')
makedepends=()
depends=()
provides=()
source=(http://snowball.tartarus.org/dist/libstemmer_c.tgz)
md5sums=('fc7f6930d843bc65e69f9151262f4153')

build() {
  cd ${srcdir}/libstemmer_c
  CC='gcc -fPIC'
  make CC="$CC"

  install -d ${pkgdir}/usr/lib
  $CC -shared -o ${pkgdir}/usr/lib/libstemmer.so $CFLAGS -Wl,--whole-archive ${srcdir}/libstemmer_c/libstemmer.o -Wl,--no-whole-archive $LDFLAGS

  install -d ${pkgdir}/usr/bin
  install ${srcdir}/libstemmer_c/stemwords ${pkgdir}/usr/bin
  install -d ${pkgdir}/usr/include
  install ${srcdir}/libstemmer_c/include/libstemmer.h ${pkgdir}/usr/include
  #install ${srcdir}/libstemmer_c/libstemmer.o ${pkgdir}/usr/lib/libstemmer.a
}
