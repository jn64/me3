# Maintainer: Your name here (*´ω｀*)

pkgname=me3-bin
pkgver=0.7.0
pkgrel=1
pkgdesc='Modding framework for FROMSOFTWARE games'
arch=('x86_64')
url='https://me3.help'
license=('Apache-2.0' 'MIT')
depends=('glibc' 'gcc-libs' 'hicolor-icon-theme')
optdepends=('steam: for supported games')
# If there is a built-from-source package
# provides=('me3')
# conflicts=('me3')
backup=('etc/me3/me3.toml')
install=me3-bin.install
source=("https://github.com/garyttierney/me3/releases/download/v$pkgver/me3-linux-amd64.tar.gz")
sha256sums=('f3c59882ff3631286adf956059a781726189afacf992d9a55fbdc57042d1b578')

prepare() {
  # TODO: Remove this after me3#416 is fixed
  cat >me3.toml <<EOF
# Workaround for Steam Linux Runtime containerised /usr
# https://github.com/garyttierney/me3/issues/416
windows_binaries_dir = '/run/host/usr/lib/me3/x86_64-windows'
EOF
}

package() {
  install -Dpm 0755 -t "$pkgdir/usr/bin" bin/me3
  install -Dpm 0644 -t "$pkgdir/usr/lib/me3/x86_64-windows" \
          bin/win64/me3-launcher.exe \
          bin/win64/me3_mod_host.dll

  install -Dpm 0644 -t "$pkgdir/usr/share/applications" dist/me3-launch.desktop
  install -Dpm 0644 -t "$pkgdir/usr/share/mime/packages" dist/me3.xml
  install -Dpm 0644 -t "$pkgdir/usr/share/icons/hicolor/128x128/apps" dist/me3.png

  install -Dpm 0644 -t "$pkgdir/usr/share/doc/$pkgname" CHANGELOG.pdf
  install -Dpm 0644 -t "$pkgdir/usr/share/licenses/$pkgname" LICENSE-APACHE LICENSE-MIT

  # TODO: Remove this after me3#416 is fixed
  install -Dpm 0644 -t "$pkgdir/etc/me3" me3.toml
}
