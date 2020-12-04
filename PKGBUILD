# Maintainer: Tomislav Ivek <tomislav.ivek@gmail.com>
# Contributor: Carl George < arch at cgtx dot us >

_name="pluginbase"
_module="$_name"

pkgname=("python-$_module")
pkgver=1.0.0
pkgrel=4
pkgdesc="A support library for building plugins systems in Python."
arch=("any")
url="http://pluginbase.pocoo.org/"
license=("BSD")
makedepends=("python-setuptools")
depends=("python")
source=("https://github.com/mitsuhiko/pluginbase/archive/$pkgver.tar.gz")
sha256sums=('ab0e5fc405f1d28abe99724943ad54b5e7fb1c2f6b1519f0942e2074e6c8c22a')

build() {
    cd "$_name-$pkgver"
    python setup.py build
}

package_python-pluginbase() {
    cd "$_name-$pkgver"
    python setup.py install --skip-build --root="$pkgdir" --optimize=1
    install -D --mode 644 --target-directory "$pkgdir/usr/share/licenses/$pkgname" LICENSE
}
