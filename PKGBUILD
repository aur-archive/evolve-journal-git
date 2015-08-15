# Maintainer: Bogdan Cuza <bogdan.cuza@hotmail.com>

_pkgname=evolve-journal
pkgname=$_pkgname-git
conflicts=("$_pkgname")
pkgver=r97.e6f029b
pkgrel=4
pkgdesc="A text editor for Evolve-OS. Git version."
arch=("any")
url="https://github.com/evolve-os/journal"
license=('GPL')
depends=("gtk3" "libsoup>=2.4" "json-glib>=1" "gtksourceview3" "vala")
makedepends=("git" "cmake>=2.6")
provides=("$_pkgname")
source=("$_pkgname::git+https://github.com/evolve-os/journal.git")
sha256sums=("SKIP")

pkgver() {
  cd "$_pkgname"
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

build() {
  cd "$_pkgname"

  cmake -DCMAKE_INSTALL_PREFIX=/usr
  make
}

package() {
  cd "$_pkgname"

  make DESTDIR="$pkgdir/" install
}
