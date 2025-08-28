pkgname=ninja
pkgver=1.13.1
pkgrel=1
pkgdesc="Small build system with a focus on speed"
arch=('x86_64')
url="https://ninja-build.org/"
license=('Apache-2.0')
depends=('gcc-libs')
makedepends=('python')
options=('!lto')
source=(https://github.com/ninja-build/ninja/archive/v${pkgver}/${pkgname}-${pkgver}.tar.gz)
sha256sums=(f0055ad0369bf2e372955ba55128d000cfcc21777057806015b45e4accbebf23)

build() {
	cd ${pkgname}-${pkgver}

    python3 configure.py --bootstrap
}

package() {
	cd ${pkgname}-${pkgver}

	install -vDm755 ninja ${pkgdir}/usr/bin/ninja

	install -vDm644 misc/bash-completion ${pkgdir}/usr/share/bash-completion/completions/ninja
	install -vDm644 misc/zsh-completion  ${pkgdir}/usr/share/zsh/site-functions/_ninja
}
