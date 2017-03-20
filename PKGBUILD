# Maintainer: William Turner <willtur.will@gmail.com>
pkgname=presto-cli
pkgver=0.169
pkgrel=1
pkgdesc='Distributed SQL Query Engine for Big Data - Client'
arch=('any')
url='https://prestodb.io/'
license=('custom:Apache 2')
depends=('java-runtime>=8' 'sh')
source=("https://repo1.maven.org/maven2/com/facebook/presto/presto-cli/${pkgver}/presto-cli-${pkgver}-executable.jar"
        'https://raw.githubusercontent.com/prestodb/presto/master/LICENSE')
noextract=("presto-cli-${pkgver}-executable.jar")
sha256sums=('a81709ae570553820131c079a343350e2297c6d5fb6e0680ceeac7fba4229d1c'
            'cfc7749b96f63bd31c3c42b5c471bf756814053e847c10f3eb003417bc523d30')

package() {
  cd "${srcdir}"

  # install in bin
  install -D -m755 "presto-cli-${pkgver}-executable.jar" "${pkgdir}/usr/bin/presto"

  # add license
  install -D -m644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
