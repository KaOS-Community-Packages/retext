pkgname=retext
pkgver=7.0.1
pkgrel=1
pkgdesc="Simple but powerful editor for Markdown and reStructuredText"
arch=('x86_64')
url="https://github.com/retext-project/retext"
license=('GPLv3')
depends=('python3' 'pyqt5-python3' 'python3-markups' 'python3-markdown' 'python3-chardet' 'python2-docutils' 'qtwebkit-tp' 'qtwebengine')
makedepends=('python3' 'qt5-tools')
source=("https://github.com/retext-project/${pkgname}/archive/${pkgver}.tar.gz")
sha256sums=('c32ccdbcf31094258c792bc0589ff3ff212dea85466d776b7f60fa7b39da4b6c')

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
