# Maintainer: David Manouchehri
# Contributor:

_gitname=
pkgname="${_gitname}-git"
_gitbranch=master
_gitauthor=
pkgdesc=""
url="https://github.com/${_gitauthor}/${_gitname}"
license=('')
source=("git://github.com/${_gitauthor}/${_gitname}#branch=${_gitbranch}")
depends=('')
makedepends=('git')
conflicts=("${_gitname}")
provides=("${_gitname}")
sha512sums=('SKIP')
arch=('aarch64' 'armv6h' 'armv7h' 'i686' 'x86_64') # arch=('any')
pkgver=0
pkgrel=1
# sha512sums_x86_64=('')
# sha512sums_i686=('')
# source_x86_64=('')
# source_i686=('')

pkgver() {
	cd "${srcdir}/${_gitname}"
	(
		set -o pipefail
		git describe --long 2>/dev/null | sed 's/\([^-]*-g\)/r\1/;s/-/./g' ||
		printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
	)
}

build() {
	cd "${srcdir}/${_gitname}"
	./autogen.sh
	./configure --prefix=/usr
	make
}

package() {
	cd "${srcdir}/${_gitname}"
}

# vim:set et sw=2 sts=2 tw=80:
