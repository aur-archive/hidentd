pkgname=hidentd
pkgver=0.4
pkgrel=3
pkgdesc="A program that implements the RFC1413 identification server"
arch=('i686' 'x86_64')
source=(http://core.segfault.pl/~hobbit/hidentd/dist/$pkgname-$pkgver.tar.gz
        hidentd)
md5sums=('2d5aa433654ccbb1009ef2c558241a17'
         'a1535701294f27d6cf6e3f0ed70f4982')
depends=('glibc' 'xinetd')
license=('custom')
backup=(etc/xinetd.d/hidentd)
url="http://core.segfault.pl/~hobbit/hidentd/"

build() {
  cd "$srcdir/$pkgname-$pkgver"
  ./configure --prefix=/usr
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"

  make prefix="$pkgdir/usr" install
  install -D -m644 "$srcdir/hidentd" "$pkgdir/etc/xinetd.d/hidentd"
}
