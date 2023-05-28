pkgname=retext
pkgver=8.0.1
pkgrel=1
pkgdesc="Simple but powerful editor for Markdown and reStructuredText"
arch=('x86_64')
url="https://github.com/retext-project/retext"
license=('GPLv3')
depends=('python3' 'pyqt6-python3' 'python3-markups' 'python3-markdown' 'python3-markdown-math' 'python3-chardet' 'python3-docutils' 'pyqt6-webengine' 'qtwebengine' 'pymdown-extensions')
makedepends=('python3' 'qt6-tools')
source=("https://github.com/retext-project/${pkgname}/archive/${pkgver}.tar.gz")
sha256sums=('8381672537b6f4dcb437a1d42aae55e87415bb6ef05d6dec33922a7fec368bcd')

prepare() {
	cd "${pkgname}-${pkgver}"
	sed -i 's|lrelease|lrelease-qt6|g' setup.py
}

build() {
	cd "${pkgname}-${pkgver}"
	lrelease-qt6 ReText/locale/*.ts
}

package() {
	cd "${pkgname}-${pkgver}"
	python3 setup.py install --root="${pkgdir}" --optimize=1
}
