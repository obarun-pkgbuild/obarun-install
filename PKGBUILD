# Maintainer: Eric Vidal <eric@obarun.org>


pkgname=obarun-install
_commit=44a073e9039e4acf5a03dc233347e0438bdccd41 # tag 0.9.0
pkgver=0.9.1
pkgrel=1
pkgdesc="Script for automatic installation"
arch=(x86_64)
url="https://github.com/Obarun/obarun-install"
license=(ISC)
depends=('arch-install-scripts' 'mc' 'git' 'pacman' 'cower' 'obarun-libs' 'obarun-install-themes')
backup=('etc/obarun/install.conf')
#source=("obarun-install::git+https://github.com/Obarun/obarun-install#tag=v${pkgver}")
source=("git+https://github.com/Obarun/obarun-install#commit=$_commit")
md5sums=('SKIP')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal

pkgver() {
	cd "${pkgname}"
	
	git describe --tags | sed -e 's:-:+:g;s:^v::'
}

package() {
	cd "${pkgname}"

	make DESTDIR="$pkgdir" install
}
