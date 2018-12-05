# Maintainer: William Turner <willtur.will@gmail.com>
pkgname=graphql-playground-electron
pkgver=1.8.4
pkgrel=1
pkgdesc="GraphQL IDE for better development workflows (GraphQL Subscriptions, interactive docs & collaboration)."
arch=('x86_64')
url="https://github.com/prisma/graphql-playground"
license=('MIT')
depends=('gtk3' 'gconf' 'nss' 'libxss')
makedepends=('sed')
source=("https://github.com/prisma/graphql-playground/releases/download/v${pkgver}/${pkgname}_${pkgver}_amd64.deb"
        "https://raw.githubusercontent.com/prisma/graphql-playground/v${pkgver}/LICENSE")
sha256sums=('c41df52d4942c25327b30501fcf85eda3bede5700bd4957051d50b3a58b00277'
            'ee88d093c7c8e10dd41fc1c7b5ff51b2bbf57937b1b88eb3c1927f57743d59db')

prepare() {
  bsdtar xf data.tar.xz
}

package() {
  mv opt "$pkgdir"
  mv usr "$pkgdir"

  install -d -m755 "${pkgdir}/usr/bin"
  ln -s "/opt/GraphQL Playground/graphql-playground-electron" "${pkgdir}/usr/bin/graphql-playground-electron"

  install -D -m644 -t "${pkgdir}/usr/share/licenses/${pkgname}" LICENSE
}
