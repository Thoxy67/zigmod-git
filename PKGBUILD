_pkgbasename=zigmod
pkgname=${_pkgbasename}-git
pkgrel=1
pkgver=r835.8fb6d24
pkgdesc="A package manager for the Zig programming language."
arch=('x86_64' 'aarch64' 'i686')
url="https://github.com/nektro/zigmod"
license=('MIT')
makedepends=('curl' 'jq' 'minisign' 'git' 'zig')
depends=('zig')
provides=('zigmod')
conflicts=('zigmod')
sha256sums=('SKIP')
source=(git+https://github.com/nektro/${_pkgbasename})

prepare() {
	cd "${srcdir}/${_pkgbasename}"
	git submodule init
	git config submodule.known-folders.url "$srcdir"/known-folders
	git submodule update
}

pkgver() {
	cd "${srcdir}/${_pkgbasename}"
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd "${srcdir}/${_pkgbasename}"
	zig build -Dmode=ReleaseSafe -j1
}

package() {
	cd "${srcdir}/${_pkgbasename}"

	install -D -m755 zig-out/bin/$_pkgbasename "${pkgdir}/usr/bin/$_pkgbasename"
	install -D -m644 LICENSE "${pkgdir}/usr/share/licenses/$_pkgbasename/LICENSE"
}

function exit_cleanup {
	rm -rf "${srcdir}/${_pkgbasename}"
	msg2 'exit cleanup done'
	remove_deps
}

trap exit_cleanup EXIT
