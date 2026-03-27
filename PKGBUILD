pkgname=bristol
pkgver=0.60.12
pkgrel=1
pkgdesc="Vintage synthesizers emulator"
arch=(i686 x86_64)
url="http://bristol.sourceforge.net"
license=('GPL')
makedepends=('gcc')
depends=('jack' 'libx11')
options=(!libtool)
source=("$pkgname-$pkgver::git+https://github.com/majorx234/bristol-fixes.git#tag=v$pkgver")

sha256sums=(SKIP)

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    ./configure --prefix=/usr --disable-version-check --enable-jack-default-audio # --enable-jack-default-midi
    make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" install
    install -v -m 0644 ChangeLog ${pkgdir}/usr/share/bristol/
    install -v -m 0644 README ${pkgdir}/usr/share/bristol/
}
