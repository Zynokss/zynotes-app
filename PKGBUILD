# Maintainer: Zynoks
# Packages the official prebuilt Zynotes release; does not build application source.
pkgname=zynotes-bin
pkgver=0.1.1
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
sha512sums=('078d9c0181af06859b4e8cb2cc6189e260b1cdccb44ddcdca612198422b3a0b96df4593496b047fbf309a7683fa3095b129986409c779f6891c200897f06452c')

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
