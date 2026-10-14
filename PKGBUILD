# Maintainer: Zynoks
# Packages the official prebuilt Zynotes release; does not build application source.
pkgname=zynotes-bin
pkgver=0.1.2
pkgrel=1
pkgdesc='Local-first personal notebooks, writing, and connected ideas'
arch=('x86_64')
url='https://zynotes.zynoks.com'
# The upstream release does not declare an application license.
license=('LicenseRef-Unknown')
depends=(
  'alsa-lib' 'at-spi2-core' 'cairo' 'dbus' 'expat' 'libgcc' 'glib2' 'hicolor-icon-theme'
  'glibc' 'gtk3' 'libcups' 'libx11' 'libxcb' 'libxcomposite' 'libxdamage'
  'libxext' 'libxfixes' 'libxkbcommon' 'libxrandr' 'mesa' 'nspr' 'nss'
  'pango' 'systemd-libs' 'xdg-utils'
)
provides=("zynotes=${pkgver}")
conflicts=('zynotes')
options=('!strip' '!debug')
source=("zynotes-${pkgver}.pacman::https://updates.zynotes.zynoks.com/zynotes-${pkgver}.pacman")
noextract=("zynotes-${pkgver}.pacman")
sha512sums=('95e147d50af8868d77abbaa6e684241bebe4763367c25b44e987d4d62c52cebf1aa20d7abe0ac8b519694f5475d0cfa756ff32900e2356bcb1770288858338e7')

prepare() {
  mkdir -p "${srcdir}/upstream"
  bsdtar -xf "${srcdir}/zynotes-${pkgver}.pacman" -C "${srcdir}/upstream"
}

package() {
  install -d "${pkgdir}/opt" "${pkgdir}/usr/share" "${pkgdir}/usr/bin"
  cp -a "${srcdir}/upstream/opt/Zynotes" "${pkgdir}/opt/"
  cp -a "${srcdir}/upstream/usr/share/." "${pkgdir}/usr/share/"
  ln -s /opt/Zynotes/zynotes "${pkgdir}/usr/bin/zynotes"
  # Chromium's sandbox helper must be root-owned and setuid in the installed package.
  chmod 4755 "${pkgdir}/opt/Zynotes/chrome-sandbox"
}
