# Maintainer: Nemo <archlinux at captnemo dot in>
pkgname=pop-bin
pkgver=5.0.10
pkgrel=1
pkgdesc="Low latency videoconferencing & screen sharing with multiplayer drawing & control. Pop is a multiplayer screen sharing app that lets you work together like you’re in the same room."
arch=('x86_64')
url="https://pop.com"
depends=('alsa-lib' 'atk' 'at-spi2-atk' 'at-spi2-core' 'cairo' 'dbus' 'desktop-file-utils' 'expat' 'gcc-libs' 'gdk-pixbuf2' 'glib2' 'glibc' 'gtk3' 'hicolor-icon-theme'  'libcups' 'libnotify' 'libutil-linux' 'libx11' 'libxcb' 'libxcomposite' 'libxcursor' 'libxdamage' 'libxext' 'libxfixes' 'libxi' 'libxrandr' 'libxrender' 'libxss' 'libxtst' 'nspr' 'nss' 'pango'  'xpra')
optdepends=('apparmor'
            'libgnome-keyring'
            'pulseaudio'
            'kde-cli-tools'
            'trash-cli'
            'xdg-utils'
            'libappindicator-gtk3')
license=('custom')
options=('!strip' '!emptydirs')
replaces=('screen-desktop-bin')
conflicts=('screen-desktop-bin')
source=("https://download.pop.com/desktop-app/linux/${pkgver}/pop_${pkgver}_amd64.deb")
sha512sums=('0812f83237a56bdc1cf48277c8f2dc18da61de403cce4c3ad1896c4679484162ea0f1479d9fdd095b422f44d745dbbe565d5dfcbb2ca0af73e63b29190ebe126')

package(){
    mkdir -p "${pkgdir}/opt/${pkgname}"
    tar xf data.tar.xz
    cp -r usr/lib/pop/* "${pkgdir}/opt/${pkgname}"

    install -dm755 "$pkgdir"/usr/bin
    ln -s /opt/"$pkgname"/Pop "$pkgdir/usr/bin/pop"

    install -D -m644 "usr/share/applications/pop.desktop" "${pkgdir}/usr/share/applications/pop.desktop"
    install -D -m644 "usr/share/pixmaps/pop.png" "${pkgdir}/usr/share/pixmaps/pop.png"
    install -D -m644 "usr/share/doc/pop/copyright" "${pkgdir}/usr/share/doc/${pkgname}/COPYRIGHT"
    install -D -m644 "usr/lib/pop/LICENSES.chromium.html" "${pkgdir}/usr/share/licenses/${pkgname}/chromium.LICENSE"
}
