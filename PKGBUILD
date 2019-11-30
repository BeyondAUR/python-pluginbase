# Maintainer: Tomislav Ivek <tomislav.ivek@gmail.com>
# Contributor: Carl George < arch at cgtx dot us >

_name="pluginbase"
_module="$_name"

pkgname=("python-$_module" "python2-$_module")
pkgver=1.0.0
pkgrel=3
pkgdesc="A support library for building plugins systems in Python."
arch=("any")
url="http://pluginbase.pocoo.org/"
license=("BSD")
makedepends=("python-setuptools" "python2-setuptools" "fakeroot")
source=("https://github.com/mitsuhiko/pluginbase/archive/$pkgver.tar.gz")
sha256sums=('ab0e5fc405f1d28abe99724943ad54b5e7fb1c2f6b1519f0942e2074e6c8c22a')

build() {
    cd "$_name-$pkgver"
    python setup.py build
    python2 setup.py build
}

package_python-pluginbase() {
    depends=("python")
    cd "$_name-$pkgver"
    python setup.py install --skip-build --root="$pkgdir" --optimize=1
    install -D --mode 644 --target-directory "$pkgdir/usr/share/licenses/$pkgname" LICENSE
}

package_python2-pluginbase() {
    depends=("python2")
    cd "$_name-$pkgver"
    python2 setup.py install --skip-build --root="$pkgdir" --optimize=1
    install -D --mode 644 --target-directory "$pkgdir/usr/share/licenses/$pkgname" LICENSE
}
