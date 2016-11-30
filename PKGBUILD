pkgname=retext
pkgver=6.0.2
pkgrel=1
pkgdesc="Simple but powerful editor for Markdown and reStructuredText"
arch=('x86_64')
url="https://github.com/retext-project/retext"
license=('GPLv3')
depends=('python3' 'pyqt5-python3' 'python3-markups' 'python3-markdown' 'python2-docutils')
makedepends=('python3' 'qt5-tools')
source=("https://github.com/retext-project/${pkgname}/archive/${pkgver}.tar.gz")
sha256sums=('50c02d69ff6dca8863003e913a2acae7f3041e44ea96852e2dac303d435d1ca2')

prepare() {
	cd "${pkgname}-${pkgver}"
	sed -i 's|lrelease|lrelease-qt5|g' setup.py
}

build() {
	cd "${pkgname}-${pkgver}"
	lrelease-qt5 locale/*.ts
}

package() {
	cd "${pkgname}-${pkgver}"
	python3 setup.py install --root="${pkgdir}" --optimize=1
}
