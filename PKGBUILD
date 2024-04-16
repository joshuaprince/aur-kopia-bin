# Maintainer: Eric Cheng <eric@chengeric.com>

pkgname=kopia-bin
pkgdesc='A cross-platform backup-tool with encryption, deduplication, compression and cloud support.'
pkgver=0.17.0
# Uncomment for releases with hyphens
# _pkgver=$(echo "$pkgver" | tr '~' -)
pkgrel=1
arch=('x86_64' 'aarch64' 'armv7h')
url='https://github.com/kopia/kopia/'
license=('APACHE')
provides=("${pkgname%-bin}")
conflicts=("${pkgname%-bin}")
optdepends=('fuse3: Needed to mount Kopia snapshots on local filesystem')
source_x86_64=("https://github.com/kopia/kopia/releases/download/v$pkgver/${pkgname%-bin}_${pkgver}_linux_amd64.deb")
source_aarch64=("https://github.com/kopia/kopia/releases/download/v$pkgver/${pkgname%-bin}_${pkgver}_linux_arm64.deb")
source_armv7h=("https://github.com/kopia/kopia/releases/download/v$pkgver/${pkgname%-bin}_${pkgver}_linux_armhf.deb")
sha256sums_x86_64=('3529928a44d613a38c6017be4eef72cde69fea81d1b97a1e772263f0d5d7acd0')
sha256sums_aarch64=('60e4dfe2f9c1c13dcc397f465c30f5e86f4ddd84dd765ed9cbb6aabb268e11b2')
sha256sums_armv7h=('2e537ee5293f692e8de8fb366ac07a1be256959a4ed1fcaa4f1779c463ec5e7e')

package() {
    tar -xf data.tar.gz -C "$pkgdir"
    "$pkgdir/usr/bin/${pkgname%-bin}" --completion-script-bash | install -Dm 644 /dev/stdin "$pkgdir/usr/share/bash-completion/completions/${pkgname%-bin}"
    "$pkgdir/usr/bin/${pkgname%-bin}" --completion-script-zsh | install -Dm 644 /dev/stdin "$pkgdir/usr/share/zsh/site-functions/_${pkgname%-bin}"
}
