# Maintainer: Yasuo Ozu <yasuo@ozu.email>

pkgname=SimPipe
pkgver=0.1.4
pkgrel=1
pkgdesc="MIPS pipeline emulator based on SimMips by Keiji Kimura"
arch=('i686' 'x86_64')
url="http://www.apal.cs.waseda.ac.jp/kimura/"
license=('GPLv2')
depends=()
makedepends=('gcc' 'make')
options=()
source=(http://www.apal.cs.waseda.ac.jp/kimura/lecture/carch/SimPipe-0.1.4.tgy SimPipe-run SimPipe-run-linux SimPipe-run-mieru)
sha256sums=('71e56cce8cb1098deacb3c38a79937893ad1fabe225d3cbf183d003f240ebee2' SKIP SKIP SKIP)

build() {
  cd "${srcdir}"
  mv SimPipe-0.1.4.tgy SimPipe-0.1.4.tgz
  tar -xzvf SimPipe-0.1.4.tgz
  cd SimPipe-0.1.4
  make
}

package() {
  mkdir -p "${pkgdir}/usr/bin" "$pkgdir/usr/share/SimPipe"
  install -m 0755 "${srcdir}/SimPipe-0.1.4/SimPipe" "${pkgdir}/usr/bin/SimPipe"
  install -m 0755 "${srcdir}/SimPipe-run" "${pkgdir}/usr/bin/SimPipe-run"
  install -m 0755 "${srcdir}/SimPipe-run-linux" "${pkgdir}/usr/bin/SimPipe-run-linux"
  install -m 0755 "${srcdir}/SimPipe-run-mieru" "${pkgdir}/usr/bin/SimPipe-run-mieru"
  cp -r "${srcdir}/SimPipe-0.1.4/SimMips" "${pkgdir}/usr/share/SimPipe"
}

