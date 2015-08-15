# Maintainer: Patrice Peterson <runiq at archlinux dot us>
# Contributor: Bharani Deepan <bharanideepan at_ gmail>
pkgname=dmenu-xft-height
pkgver=4.5
pkgrel=2
pkgdesc="Dynamic X menu - with Xft support and height patch"
url="http://tools.suckless.org/dmenu/"
arch=('i686' 'x86_64')
license=('MIT')
depends=('sh' 'libxinerama' 'libxft')
conflicts=('dmenu')
provides=('dmenu')
source=(http://dl.suckless.org/tools/dmenu-$pkgver.tar.gz
        dmenu-4.5-xft.diff
        dmenu-4.5-xft-height.diff)
md5sums=('9c46169ed703732ec52ed946c27d84b4'
         '0c73d595eb78f159bea83f33bba15e80'
         'dd511592290157ce9d31d37ecffb4d16')

build() {
	cd "$srcdir/dmenu-$pkgver"
	patch -p1 < ../dmenu-$pkgver-xft.diff 
	patch -p1 < ../dmenu-$pkgver-xft-height.diff 
	make 
}
package()
{
    cd "$srcdir/dmenu-$pkgver"
    make DESTDIR="$pkgdir" PREFIX=/usr install 
    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"

}
