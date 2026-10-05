pkgname=cps-limiter
pkgver=1.0.1
pkgrel=1
pkgdesc="Limits your CPS to prevent penalties for exceeding the CPS limit in various games"
arch=('x86_64')
url="https://github.com/DeusTux/CPS-Limiter"
license=('GPLv3')
depends=('qt6-base')
makedepends=('cmake' 'gcc')
source=("$pkgname-$pkgver.tar.gz::$url/archive/refs/tags/v$pkgver.tar.gz")
sha256sums=('SKIP')
_source_dir="CPS-Limiter-$pkgver"

build() {
    cmake -B build -S "$srcdir/$_source_dir"
    cmake --build build --target all
}

package() {
    install -Dm755 build/cps-limiter "$pkgdir/usr/bin/cps-limiter"
    install -Dm755 build/cps-limiter-cli "$pkgdir/usr/bin/cps-limiter-cli"
    install -Dm644 -t "$pkgdir/usr/share/cps-limiter/" "$srcdir/$_source_dir"/assets/*
    install -Dm644 "$srcdir/$_source_dir"/cps-limiter.desktop "$pkgdir/usr/share/applications/cps-limiter.desktop"
}
