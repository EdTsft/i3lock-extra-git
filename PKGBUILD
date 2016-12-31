# Maintainer: Eric Langlois <eric@langlois.xyz>

pkgname=i3lock-extra-git
pkgver=0.1.0.r0.g244eb28
pkgrel=1

pkgdesc='Wrapper around i3lock to display a modified screenshot as the lock image.'
arch=('any')
url="https://github.com/EdTsft/i3lock-extra"
license=('BSD2')

depends=('i3lock' 'scrot' 'imagemagick')
makedepends=('git')

source=("$pkgname::git+https://github.com/EdTsft/${pkgname%-git}.git")
md5sums=('SKIP')

pkgver() {
  cd "$pkgname"
  git describe --long | sed 's/^v//; s/-/.r/; s/-/./'
}

build() {
  cd "$pkgname"
  make
}

package() {
  cd "$pkgname"
  make DESTDIR="$pkgdir/" install
  install -Dm644 LICENSE "$pkgdir"/usr/share/licenses/"$pkgname"/LICENSE
}

# vim:set ts=2 sw=2 et:
