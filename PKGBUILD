# Maintainer: Nyarcel <nyarcel AT SPAMFREE gmail DOT com>

_pkgname=polylib

pkgname=$_pkgname-no-gmp-git
pkgver=5.22.5.r18.g8080293
pkgrel=1
pkgdesc='A library of polyhedral functions, without GMP.'
arch=('any')
url='http://icps.u-strasbg.fr/polylib/'
license=('GPL3')
provides=('polylib')
conflicts=('polylib' 'polylib-git')
makedepends=('git')
source=("$_pkgname-git::git://repo.or.cz/polylib")
md5sums=('SKIP')

pkgver() {
	cd "$_pkgname-git"
	git describe --long --tags | sed -r 's/^polylib-//;s/([^-]*-g)/r\1/;s/-/./g'
}

build() {
	cd "$_pkgname-git"
	autoreconf -i
	./configure --prefix=/usr
	make
}

check() {
	cd "$_pkgname-git"
	make tests
}

package() {
	cd "$_pkgname-git"
	make DESTDIR="$pkgdir/" install
}
