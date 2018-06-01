# Maintainer: Eric Vidal <eric@obarun.org>
# based on the original https://git.archlinux.org/svntogit/community.git/tree/trunk?h=packages/pacman-contrib
# 						Maintainer: Johannes Löthberg <johannes@kyriasis.com>

pkgname=pacman-contrib
pkgver=1.0.0
pkgrel=3
pkgdesc="Contributed scripts and tools for pacman systems"
url="https://git.archlinux.org/pacman-contrib.git/about/"
arch=('x86_64')
license=('GPL')
depends=('pacman' 'fakeroot')
optdepends=('mlocate: pacdiff'
            'findutils: pacdiff')
makedepends=('asciidoc')
source=(https://sources.archlinux.org/other/community/pacman-contrib/pacman-contrib-$pkgver.tar.gz)
sha256sums=('0fb95514bd16a316d4cce920d34edc88b0d0618c484e2d7588746869d2339795')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal

build() {
  cd pacman-contrib-$pkgver

  ./configure \
      --prefix=/usr \
      --sysconfdir=/etc \
      --localstatedir=/var
  make
}

check() {
  make -C pacman-contrib-$pkgver check
}

package() {
  cd pacman-contrib-$pkgver

  make DESTDIR="$pkgdir" install
}
