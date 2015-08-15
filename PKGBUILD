# Maintainer: jsteel <mail at jsteel dot org>
# Contributor: Daniel J Griffiths <ghost1227@archlinux.us>
# Contributor: Stefan Clarke <fm0nk3y@yahoo.co.uk>

pkgname=gnubg
pkgver=1.00.0
_pkgver=1_00_000
pkgrel=1
pkgdesc="A world class backgammon application"
arch=('i686' 'x86_64')
url="http://www.gnubg.org"
license=('GPL')
depends=('python2' 'gtkglext' 'hicolor-icon-theme' 'mesa')
conflicts=('gnubg-cli' 'gnubg-cvs')
install=$pkgname.install
source=($url/media/sources/$pkgname-release-$_pkgver-sources.tar.gz
        $pkgname.desktop)
md5sums=('49d874dc9a77c5045016a615e3ed93f4'
         '965f5c7c25f60b27d06cc6fef7befd30')

build() {
  cd "$srcdir"

  ./autogen.sh

  ./configure --prefix=/usr --bindir=/usr/bin --sysconfdir=/etc \
    --mandir=/usr/share/man

  make
}

package() {
  cd "$srcdir"

  make DESTDIR="$pkgdir"/ install

  install -Dm644 "$srcdir"/$pkgname.desktop \
    "$pkgdir"/usr/share/applications/$pkgname.desktop
}
