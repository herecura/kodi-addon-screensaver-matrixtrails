# $Id$
# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-screensaver-matrixtrails
_commit=8cebb75
pkgver=20160523.8cebb75
pkgrel=1
pkgdesc="Matrix trails screensaver for Kodi"
arch=('i686' 'x86_64')
url='github.com/notspiff/screensaver.matrixtrails'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-screensaver')
depends=('kodi' 'soil')
makedepends=('git' 'cmake')
source=("$pkgname::git://github.com/notspiff/screensaver.matrixtrails.git#commit=$_commit")
sha256sums=('SKIP')

pkgver() {
	cd "$pkgname"
	git log -1 --date=short --format="%cd.%h" | tr -d '-'
}

build() {
	cd "$pkgname"
	cmake \
		-DCMAKE_INSTALL_PREFIX=/usr \
		-DCMAKE_BUILD_TYPE=Release \
		-DBUILD_SHARED_LIBS=1 \
		-DUSE_LTO=1
	make
}

package() {
	cd "$pkgname"
	make DESTDIR="$pkgdir/" install
}

