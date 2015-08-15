# Maintainer:  mac1202
# Contributor: prettyvanilla <prettyvanilla@posteo.at>
# Contributor: almostalive   <almostalive2003 at gmail dot com>

pkgname=beetle-pce-fast-libretro-git
pkgver=584.bbc4d0f
pkgrel=1
pkgdesc="Standalone port of Mednafen PCE Fast to libretro."
arch=('i686' 'x86_64' 'arm' 'armv6h')
url="https://github.com/libretro/beetle-pce-fast-libretro"
license=('GPL')
makedepends=('git')
conflicts=('libretro-mednafen-pce-git')

_gitname=beetle-pce-fast-libretro
source=("git+https://github.com/libretro/${_gitname}.git"
        "https://raw.github.com/libretro/libretro-super/master/dist/info/mednafen_pce_fast_libretro.info")
md5sums=('SKIP'
         'SKIP')

pkgver() {
  cd "${_gitname}"
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

build() {
  cd "${_gitname}"
  make
}

package() {
  install -Dm644 "${_gitname}/mednafen_pce_fast_libretro.so" "${pkgdir}/usr/lib/libretro/libretro-mednafen-pce.so"
  install -Dm644 "mednafen_pce_fast_libretro.info" "${pkgdir}/usr/lib/libretro/libretro-mednafen-pce.info"
}
