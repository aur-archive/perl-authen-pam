# CPAN Name  : Authen-Simple-LDAP
# Contributor: Christian Hesse <mail@earthworm.de>

pkgname='perl-authen-pam'
pkgver='0.16'
pkgrel='1'
pkgdesc="Perl interface to PAM library"
arch=('any')
url="http://search.cpan.org/~nikip/Authen-PAM-$pkgver/"
license=('unknown')
depends=('perl')

options=('!emptydirs')

source=("http://search.cpan.org/CPAN/authors/id/N/NI/NIKIP/Authen-PAM-$pkgver.tar.gz")
md5sums=('7278471dfa694d9ef312bc92d7099af2')

build() {
  DIST_DIR="${srcdir}/Authen-PAM-$pkgver"
  export PERL_AUTOINSTALL=--skipdeps PERL_MM_USE_DEFAULT=1
  {
	cd "$DIST_DIR" &&
    perl Makefile.PL INSTALLDIRS=vendor &&
    make &&
    make test &&
    make DESTDIR="$pkgdir" install;
  } || return 1;

  find "$pkgdir" -name .packlist -o -name perllocal.pod -delete
}
