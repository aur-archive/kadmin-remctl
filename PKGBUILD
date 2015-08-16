# Maintainer: Mantas M. <grawity@gmail.com>
pkgname=kadmin-remctl
pkgver=3.6
pkgrel=1
pkgdesc="remctl backend that implements basic Kerberos account administration functions"
arch=("i686" "x86_64")
url="http://www.eyrie.org/~eagle/software/kadmin-remctl/"
license=("custom")
depends=("krb5" "remctl")
backup=("etc/remctl/conf.d/kadmin"
        "etc/remctl/conf.d/password")
source=("http://archives.eyrie.org/software/kerberos/$pkgname-$pkgver.tar.gz"
        "http://archives.eyrie.org/software/kerberos/$pkgname-$pkgver.tar.gz.asc")
sha1sums=('b0882124584d490550f3628e9d0a3853fe7794a6'
          'SKIP')
validpgpkeys=('E784364E8DDE7BB370FBD9EAD15D313882004173')

build() {
  cd "$srcdir/$pkgname-$pkgver"
  ./configure \
    --prefix=/usr \
    ;
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make DESTDIR="$pkgdir" install
  install -Dm0644 LICENSE         "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  install -Dm0644 README          "$pkgdir/usr/share/doc/$pkgname/README"
  install -Dm0644 docs/design     "$pkgdir/usr/share/doc/$pkgname/design"
  install -Dm0644 remctl/kadmin   "$pkgdir/etc/remctl/conf.d/kadmin"
  install -Dm0644 remctl/password "$pkgdir/etc/remctl/conf.d/password"
}

# vim: ts=2:sw=2:et:ft=sh
