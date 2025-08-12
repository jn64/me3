# Maintainer: 

pkgname=me3-bin
pkgver=0.7.0
pkgrel=1
pkgdesc='Modding framework for FROMSOFTWARE games'
arch=('x86_64')
url='https://me3.help'
license=('Apache-2.0' 'MIT')
optdepends=('steam: for supported games')
# If there is a built-from-source package
# provides=('me3')
# conflicts=('me3')
source=("https://github.com/garyttierney/me3/releases/download/v$pkgver/me3-linux-amd64.tar.gz")
sha256sums=('f3c59882ff3631286adf956059a781726189afacf992d9a55fbdc57042d1b578')

package() {
  install -Dpm 0755 -t "$pkgdir/usr/bin" bin/me3
  install -Dpm 0644 -t "$pkgdir/usr/lib/me3/x86_64-windows" \
          bin/win64/me3-launcher.exe \
          bin/win64/me3_mod_host.dll

  install -Dpm 0644 -t "$pkgdir/usr/share/applications" dist/me3-launch.desktop
  install -Dpm 0644 -t "$pkgdir/usr/share/mime/packages" dist/me3.xml
  install -Dpm 0644 -t "$pkgdir/usr/share/icons/hicolor/128x128/apps" dist/me3.png

  install -Dpm 0644 -t "$pkgdir/usr/share/doc/me3" CHANGELOG.pdf
  install -Dpm 0644 -t "$pkgdir/usr/share/licenses/me3" LICENSE-APACHE LICENSE-MIT
}
