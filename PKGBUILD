# $Id: PKGBUILD 142448 2015-10-01 16:05:48Z fyan $
# Maintainer: Massimiliano Torromeo <massimiliano.torromeo@gmail.com>
# Maintainer: Felix Yan <felixonmars@archlinux.org>
# Contributor: Ralf Schmitt <ralf@systemexit.de>

pkgbase=python-greenlet
pkgname=(python-greenlet python2-greenlet)
pkgver=0.4.9
pkgrel=2
pkgdesc="Lightweight in-process concurrent programming"
license=("MIT")
url="http://pypi.python.org/pypi/greenlet"
makedepends=('python-setuptools' 'python2-setuptools')
source=("https://pypi.python.org/packages/source/g/greenlet/greenlet-${pkgver}.zip")
arch=('i686' 'x86_64')

prepare() {
    cp -a greenlet-$pkgver greenlet-$pkgver-py2
}

build() {
	cd greenlet-$pkgver
	python setup.py build

    cd ../greenlet-$pkgver-py2
    python2 setup.py build
}

check() {
    cd greenlet-$pkgver
    python setup.py test

    cd ../greenlet-$pkgver-py2
    python2 setup.py test
}

package_python-greenlet() {
    depends=('python')

    cd greenlet-$pkgver
    python setup.py install -O1 --root="$pkgdir"
    install -Dm0644 LICENSE.PSF "$pkgdir/usr/share/licenses/$pkgname/LICENSE.PSF"
}

package_python2-greenlet() {
    depends=('python2')

	cd greenlet-$pkgver-py2
	python2 setup.py install -O1 --root="$pkgdir"
	install -Dm0644 LICENSE.PSF "$pkgdir/usr/share/licenses/$pkgname/LICENSE.PSF"
}

sha512sums=('2dce966827caf32b21cf005498ef6e595524ffb0aabbe424c705850986edfda4f4b2ba791180a7de900b1778594851de83a5b2cc69baf31c968ee8fb9131ba58')
