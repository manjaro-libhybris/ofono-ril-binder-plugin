#Maintainer Erik Inkinen <erik.inkinen@gmail.com>
pkgname=ofono-ril-binder-plugin
provides=('ofono-ril-binder-plugin')
_pkgbase=ofono-ril-binder-plugin
pkgver=105.b5050bc
pkgrel=1
arch=('armv7h' 'aarch64' 'x86' 'x86_64')
url="https://github.com/mer-hybris/ofono-ril-binder-plugin"
license=('BSD')
depends=('libgbinder' 'libgbinder-radio' 'libgrilio' 'ofono')
makedepends=('git' 'pkgconfig')
source=("ofono-ril-binder-plugin::git+https://github.com/mer-hybris/ofono-ril-binder-plugin.git")
md5sums=('SKIP')
options=(debug !strip)

pkgver() {
  cd "${srcdir}/${_pkgbase}"
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

build() {
  cd "${srcdir}/${_pkgbase}"
  make LIBDIR=/usr/lib KEEP_SYMBOLS=1 release pkgconfig
}

package() {
  cd "${srcdir}/${_pkgbase}"
  make LIBDIR=/usr/lib DESTDIR="$pkgdir/" install-dev
}

