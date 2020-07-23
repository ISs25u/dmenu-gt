_pkgname=dmenu
pkgname=dmenu-gt-git
pkgver=4.6.2
pkgrel=1
pkgdesc="GT's build of dmenu"
url="https://github.com/ISs25u/dmenu-gt"
arch=('i686' 'x86_64')
license=('MIT')
depends=('sh' 'libxinerama' 'libxft')
makedepends=('git')
provides=($_pkgname)
conflicts=($_pkgname)
source=("git+$url.git")
sha256sums=('SKIP')

pkgver() {
  cd "${_pkgname}-gt"
  printf '%s' "$pkgver"
}

build(){
  cd "${_pkgname}-gt"
  make \
    X11INC=/usr/include/X11 \
    X11LIB=/usr/lib/X11
}

package() {
  cd "${_pkgname}-gt"
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -Dm644 LICENSE "$pkgdir"/usr/share/licenses/$pkgname/LICENSE
}
