# Maintainer: ava1ar <mail(at)ava1ar(dot)info>

pkgname=chromium-libpdf-stable
pkgdesc="Google Chrome's PDF plugin for Chromium (stable version)"
pkgver=32.0.1700.77
pkgrel=1
_verbld=${pkgver}-1
_channel='stable'
arch=('i686' 'x86_64')
url="http://www.google.com/chrome"
license=('custom:chrome')
depends=('chromium')
source=(license.html::http://www.google.com/chrome/intl/en/eula_text.html)
sha1sums=('SKIP')
if [ "$CARCH" == x86_64 ]; then
        source+=(https://dl.google.com/linux/chrome/rpm/stable/x86_64/google-chrome-${_channel}-${_verbld}.x86_64.rpm)
        sha1sums+=('79c64dfc62fc0c58ac0510f8b1fb3730a3e733f8')
elif [ "$CARCH" == i686 ]; then
        source+=(https://dl.google.com/linux/chrome/rpm/stable/i386/google-chrome-${_channel}-${_verbld}.i386.rpm)
        sha1sums+=('71d196029d1c31518aeffe8f93f73280a389b105')
fi

package() {
    install -d "${pkgdir}/usr/lib/chromium"
    install -m644 opt/google/chrome/libpdf.so "${pkgdir}/usr/lib/chromium"
    install -Dm644 "${srcdir}/license.html" "${pkgdir}/usr/share/licenses/${pkgname}/license.html"
}
