# Maintainer: Konstantin Shalygin <k0ste@k0ste.ru>
# Contributor: Konstantin Shalygin <k0ste@k0ste.ru>

pkgname='libyang'
pkgver='2.2.8'
pkgrel='1'
pkgdesc='A YANG data modelling language parser and toolkit written (and providing API) in C'
url="https://github.com/CESNET/${pkgname}"
arch=('x86_64' 'aarch64' 'armv7h')
license=('BSD')
depends=('pcre2')
makedepends=('cmake' 'doxygen' 'graphviz')
checkdepends=('cmocka')
conflicts=('libyang-git' 'libyang-devel-git')
source=("${url}/archive/v${pkgver}.tar.gz")
sha256sums=('301e134acbaa1f3eb1e5db0a996ce4bc9ff32de61c98f5fe3192e6cc84429dd3')

prepare() {
  cd "${pkgname}-${pkgver}"
  mkdir build
}

build() {
  cd "${pkgname}-${pkgver}/build"
  cmake .. \
    -DCMAKE_INSTALL_PREFIX="/usr" \
    -DCMAKE_INSTALL_LIBDIR="lib" \
    -DCMAKE_BUILD_TYPE="Release" \
    -DENABLE_TESTS="ON"
  make
}

check() {
  cd "${pkgname}-${pkgver}/build"
  ctest
}

package() {
  cd "${pkgname}-${pkgver}/build"
  make DESTDIR="${pkgdir}" install
  install -Dm644 "../LICENSE" -t "${pkgdir}/usr/share/licenses/${pkgname}"
}
