pkgname=perl-net-http
pkgver=6.09
pkgrel=1
pkgdesc="Low-level HTTP connection (client)"
arch=('x86_64')
url=http://search.cpan.org/dist/Net-HTTP
license=('PerlArtistic' 'GPL')
options=('!emptydirs')
depends=('perl')
checkdepends=('perl-uri')
conflicts=('perl-libwww<6')
source=("http://cpan.metacpan.org/authors/id/E/ET/ETHER/Net-HTTP-$pkgver.tar.gz")
md5sums=('3d84d17f64c7316d69e7eb7b4e292b9a')

build() {
    export PERL_MM_USE_DEFAULT=1 PERL5LIB=""                 \
      PERL_AUTOINSTALL=--skipdeps                            \
      PERL_MM_OPT="INSTALLDIRS=vendor"     \
      PERL_MB_OPT="--installdirs vendor" \
      MODULEBUILDRC=/dev/null

    cd Net-HTTP-${pkgver}
    /usr/bin/perl Makefile.PL
    make
}

check() {
    export PERL_MM_USE_DEFAULT=1 PERL5LIB=""
    cd Net-HTTP-${pkgver}
    make test
}

package() {
    cd Net-HTTP-${pkgver}
    make DESTDIR="$pkgdir" install
}
