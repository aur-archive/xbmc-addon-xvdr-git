# Maintainer  : Olaf Bauer <hydro@freenet.de>

pkgname=xbmc-addon-xvdr-git
pkgver=20140329
pkgrel=1
pkgdesc="PVR add-on for XBMC to add VDR as a TV/PVR Backend to XBMC"
arch=('i686' 'x86_64')
url="https://github.com/pipelka/xbmc-addon-xvdr"
license=('GPL2')
depends=('xbmc')
conflicts=('xbmc-addon-xvdr')
provides=('xbmc-addon-xvdr')
makedepends=('git')
source=('git+https://github.com/pipelka/xbmc-addon-xvdr')
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/xbmc-addon-xvdr"
  git log -1 --format="%cd" --date=short | tr -d '-'
}

build() {
  cd "$srcdir/xbmc-addon-xvdr"
  sh autogen.sh
  ./configure --prefix=/usr/lib/xbmc
  make
}

package() {
  cd "$srcdir/xbmc-addon-xvdr"
  make DESTDIR="${pkgdir}/" install
}
