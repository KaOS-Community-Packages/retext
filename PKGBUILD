pkgname=retext
pkgver=8.0.2
pkgrel=2
pkgdesc="Simple but powerful editor for Markdown and reStructuredText"
arch=('x86_64')
url="https://github.com/retext-project/retext"
license=('GPLv3')
depends=('python3' 'pyqt6-python3' 'python-markups' 'python3-markdown' 'python-markdown-math' 'python3-chardet' 'python3-docutils' 'pyqt6-webengine' 'qtwebengine' 'pymdown-extensions')
makedepends=('python3' 'qt6-tools')
source=("https://github.com/retext-project/${pkgname}/archive/${pkgver}.tar.gz")
sha256sums=('e40a1243767a9455870a86920f8ba4f35dff90d08bfe43da038a617136328d2b')

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
