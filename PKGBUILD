# Maintainer: Eric Vidal <eric@obarun.org>


pkgname=obarun-install
_commit=0d14116a236d4dd175ae21d3063956f307504b2e # tag 0.8.9 move syslinux installation to the main install, fix pacman installation bug
pkgver=0.8.9
pkgrel=2
pkgdesc=" Script for automatic installation"
arch=(x86_64)
url="https://github.com/Obarun/obarun-install"
license=('BEERWARE')
depends=('arch-install-scripts' 'mc' 'git' 'pacman' 'cower' 'obarun-libs' 'obarun-install-themes')
backup=('etc/obarun/install.conf')
#install=
#source=("obarun-install::git+https://github.com/Obarun/obarun-install#tag=v${pkgver}")
source=("git+https://github.com/Obarun/obarun-install#commit=$_commit")
md5sums=('SKIP')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal

package() {
	cd "$srcdir/$pkgname"
	
	install -Dm 0755 "obarun-install.in" "$pkgdir/usr/bin/obarun-install"
	install -Dm 0755 "install.sh" "$pkgdir/usr/lib/obarun/install.sh"
	install -dm 0755 "$pkgdir/usr/lib/obarun/install/"
	for file in install/{aur.sh,bootloader.sh,choose.sh,config.sh,define.sh,pac.sh,util.sh};do
		install -Dm 0755 "${file}" "$pkgdir/usr/lib/obarun/install/"
	done
	install -Dm 0644 "install.conf" "$pkgdir/etc/obarun/install.conf"
	install -dm 0755 "$pkgdir/usr/share/licenses/obarun-install/"
	install -Dm 0644 "LICENSE" "$pkgdir/usr/share/licenses/obarun-install/LICENSE"
	install -Dm 0644 "PKGBUILD" "$pkgdir/var/lib/obarun/obarun-install/update_package/PKGBUILD"
	
	install -dm 0755 "$pkgdir/var/lib/obarun/obarun-install/config"	

}
