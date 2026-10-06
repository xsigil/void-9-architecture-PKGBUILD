# Maintainer: parorafia (@xsigil) <parorafia@xsigil.dev>
# Domain: Resilient Systems, Cyber Defense & Sovereign Application Architecture

pkgname=void-9-architecture
pkgver=0.1.0
pkgrel=1
pkgdesc="Hyper-minimalist sovereign architecture engine and kernel confinement perimeter"
arch=('x86_64' 'aarch64')
url="https://github.com/xsigil/void-9-architecture"
license=('MIT')
depends=('util-linux' 'bash')
makedepends=('go')
provides=('void')
conflicts=('void')
source=("${pkgname}-${pkgver}.tar.gz::https://github.com/xsigil/void-9-architecture/archive/refs/tags/v${pkgver}.tar.gz")
sha256sums=('SKIP')

build() {
    cd "${pkgname}-${pkgver}"
    export CGO_ENABLED=0
    export GOFLAGS="-trimpath"
    make build
}

check() {
    cd "${pkgname}-${pkgver}"
    # Verify binary self-executes cleanly
    ./bin/void help > /dev/null
}

package() {
    cd "${pkgname}-${pkgver}"

    # Install sovereign engine binary
    install -Dm755 bin/void "${pkgdir}/usr/bin/void"

    # Install documentation
    install -Dm644 README.md "${pkgdir}/usr/share/doc/${pkgname}/README.md"

    # Install license if present
    if [[ -f LICENSE ]]; then
        install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
    fi
}