# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Pellegrino Prevete (dvorak) <pellegrinoprevete@gmail.com>
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Felix Yan <felixonmars@archlinux.org>
# Contributor: Jelle van der Waa <jelle@vdwaa.nl>
# Contributer: Allan McRae <allan@archlinux.org>

_py="python"
_pkg="six"
pkgname="${_py}-${_pkg}"
pkgver=1.16.0
pkgrel=8
pkgdesc="Python 2 and 3 compatibility utilities"
arch=(
  'any'
)
url="https://pypi.python.org/pypi/six/"
license=(
  'MIT'
)
depends=(
  "${_py}"
)
makedepends=(
  "${_py}-setuptools"
)
checkdepends=(
  "${_py}-pytest"
  'tk'
)
_pypi="https://pypi.io/packages/source"
source=(
  "${_pypi}/${_pkg::1}/${_pkg}/${_pkg}-${pkgver}.tar.gz"
)
sha512sums=(
  '076fe31c8f03b0b52ff44346759c7dc8317da0972403b84dfe5898179f55acdba6c78827e0f8a53ff20afe8b76432c6fe0d655a75c24259d9acbaa4d9e8015c0'
)

check() {
  cd \
    "${_pkg}-${pkgver}"
  "${_py}" \
    -m \
      pytest
}

package() {
  cd \
    "${_pkg}-${pkgver}"
  "${_py}" \
    setup.py \
      install \
        --root="${pkgdir}" \
        --optimize=1
  install \
    -Dm644 \
    LICENSE \
    -t \
    "${pkgdir}/usr/share/licenses/${pkgname}"
}

# vim: ft=sh syn=sh et
