# Maintainer: Joshua Prince <aur _a_ jtprince _d_ com>

pkgname=kopia-bin
pkgdesc='A cross-platform backup-tool with encryption, deduplication, compression and cloud support.'
pkgver=0.18.1
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
sha256sums_x86_64=('1db613e0d8e74b98fe2d0e960e42c1b278b1128503b1bef20dc9b0f34c7656a7')
sha256sums_aarch64=('288dd864eae39c7d20e5b65a83c8a77d766dd5dd93a25b3ea8ec8c4140dfabf6')
sha256sums_armv7h=('5fe3c5c9118f3848d1d4f9d7bc31302dc0c71a8b77bca207fb3ebc139f36a40a')

package() {
    tar -xf data.tar.gz -C "$pkgdir"
    "$pkgdir/usr/bin/${pkgname%-bin}" --completion-script-bash | install -Dm 644 /dev/stdin "$pkgdir/usr/share/bash-completion/completions/${pkgname%-bin}"
    "$pkgdir/usr/bin/${pkgname%-bin}" --completion-script-zsh | install -Dm 644 /dev/stdin "$pkgdir/usr/share/zsh/site-functions/_${pkgname%-bin}"
}
