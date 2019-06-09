# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Aaron Moore <aaron@atamisk.net>
pkgname=gllock-git
_pkgname_nogit=${pkgname%-git}
pkgver=r62.e83f263
pkgrel=1
epoch=
pkgdesc="Not so simple opengl based X display locker utility"
arch=('x86_64')
url="https://github.com/kuravih/gllock"
license=('MIT')
depends=()
makedepends=()
optdepends=()
source=("git+https://github.com/kuravih/gllock.git")
noextract=()
md5sums=('SKIP')

pkgver() {
  cd "$_pkgname_nogit"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
  cd "$srcdir/$_pkgname_nogit"
  patch < ../../install-patch.patch
}

build() {
	cd "$srcdir/$_pkgname_nogit"
	pwd
	make all
}

package() {
	cd "$srcdir/$_pkgname_nogit"
	make DESTDIR="$pkgdir/" install
}
