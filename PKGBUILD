# Maintainer: lestb <tkhdlstfl dot l plus aur at gmail dot com>
# Package Repository: https://github.com/mij-aur-packages/pyhamcrest

_pypi_pkgname=PyHamcrest
pkgname=python-pyhamcrest
pkgver=2.0.2
pkgrel=1
pkgdesc='A framework for writing matcher objects, allowing you to declaratively define "match" rules'
arch=('any')
url="https://github.com/hamcrest/PyHamcrest"
license=('BSD')
depends=('python>=3.5')
makedepends=(python-setuptools)
source=("https://pypi.python.org/packages/source/P/${_pypi_pkgname}/${_pypi_pkgname}-${pkgver}.tar.gz")
sha256sums=('412e00137858f04bde0729913874a48485665f2d36fe9ee449f26be864af9316')

build() {
    _dir="${srcdir}/python-${_pypi_pkgname}-${pkgver}"
    mkdir -p "${_dir}"
    cd "${_dir}"
    cp -r "${srcdir}/${_pypi_pkgname}-${pkgver}"/. .
    python setup.py build
}

package() {
    cd "${srcdir}/python-${_pypi_pkgname}-${pkgver}"
    python setup.py install --root="${pkgdir}" --optimize=1
    install -D -m644 LICENSE.txt "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
