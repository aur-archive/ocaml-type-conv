# Maintainer: Charles E. Hawkins <charlesthehawk@yahoo.com>
# Contributor: Aaron Chen <nextAaron at gmail.com>
# Contributor: Serge Zirukin <ftrvxmtrx@gmail.com>
# Contributor: Sergei Lebedev <superbobry@gmail.com>
# Contributor : Nicolas Pouillard <nicolas(dot)pouillard(at)gmail(dot)com>
# Contributor: Sylvester Johansson <scj(at)archlinux(dot)us>

pkgname=ocaml-type-conv
_pkgname=type_conv
pkgver=111.13.00
pkgrel=2
pkgdesc="Generates code from type specifications"
arch=(i686 x86_64)
url="http://http://janestreet.github.io"
license=(LGPL)
depends=(ocaml)
makedepends=(ocaml-findlib)
source=(https://ocaml.janestreet.com/ocaml-core/$pkgver/individual/$_pkgname-$pkgver.tar.gz)
md5sums=('621e4048df864d6877b99de4b35f9bff')
options=(!strip !makeflags)

build() {
  cd "$srcdir/$_pkgname-$pkgver"

  ./configure --disable-debug --prefix /usr --destdir "$pkgdir"
  make all
}

package(){
  cd "$srcdir/$_pkgname-$pkgver"

  export OCAMLFIND_DESTDIR="$pkgdir$(ocamlfind printconf destdir)"
  install -dm 755 "$OCAMLFIND_DESTDIR"
  make install
}
