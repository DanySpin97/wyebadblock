# Maintainer: jun7 <jun7@hush.com>
pkgname=wyebadblock-git
pkgver=1.1
pkgrel=1
pkgdesc="A adblock extension for wyeb, also webkit2gtk browsers may be."
arch=('x86_64')
url="https://github.com/jun7/wyebadblock"
license=('GPL3')
depends=('webkit2gtk')
makedepends=('git')
_branch=master
source=("git://github.com/jun7/wyebadblock.git#branch=$_branch")
md5sums=('SKIP')

pkgver(){
	cd "$srcdir/wyebadblock"
	printf "$pkgver.%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
	cd "$srcdir/wyebadblock"
	git pull --rebase origin $_branch
}

build() {
	cd "$srcdir/wyebadblock"
	make
}

package() {
	cd "$srcdir/wyebadblock"
	install -Dm755 adblock.so   "$pkgdir/usr/lib/wyebrowser/adblock.so"
}
