# Maintainer: Limao Luo <luolimao+AUR@gmail.com>
# Contributor: Chris Brannon <cmbrannon79@gmail.com>
# Contributor: François Charette <firmicus@gmx.net>

pkgname=libxml-perl
pkgver=0.08
pkgrel=4
pkgdesc="Perl library for working with XML"
arch=(any)
url=http://search.cpan.org/~KMACLEOD/$pkgname
license=(GPL PerlArtistic)
depends=(perl-xml-parser)
options=(!emptydirs)
source=(http://www.cpan.org/authors/id/K/KM/KMACLEOD/$pkgname-$pkgver.tar.gz)
sha256sums=('4571059b7b5d48b7ce52b01389e95d798bf5cf2020523c153ff27b498153c9cb')
sha512sums=('66c1874a04b746334d4324ab37ee057c6da7fa7191dffae2900e0832dab3b2ededc5cbdc5e838c0d57c22161c9cf196ab40b62f61338d4c994bda9fa7b1a7702')

build() {
    cd $pkgname-$pkgver/
    perl Makefile.PL INSTALLDIRS=vendor PERL_MM_USE_DEFAULT=1
    make
}

package() {
    make -C $pkgname-$pkgver/ DESTDIR="$pkgdir" install
    find "$pkgdir" -name '.packlist' -delete
    find "$pkgdir" -name '*.pod' -delete
}
