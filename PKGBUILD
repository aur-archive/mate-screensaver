# Maintainer : Martin Wimpress <code@flexion.org>
# Contributor: Giovanni Ricciardi <kar98k.sniper@gmail.com>

pkgname=mate-screensaver
pkgver=1.6.1
pkgrel=6
pkgdesc='Screensaver for MATE'
url="http://mate-desktop.org"
arch=('i686' 'x86_64' 'armv6h' 'armv7h')
license=('GPL')
depends=('dbus-glib' 'libmatekbd' 'libnotify' 'libxss' 'mate-desktop'
         'mate-menus' 'mate-session-manager')
makedepends=('mate-common' 'mate-doc-utils' 'perl-xml-parser' 'xmlto')
optdepends=('mate-power-manager: Add power management support.')
options=('!emptydirs')
groups=('mate-extra')
source=("http://pub.mate-desktop.org/releases/1.6/${pkgname}-${pkgver}.tar.xz"
        mate-screensaver.pam)
sha1sums=('3b4c0c1554fdf96def14efa8f9e100d29dc05984'
          '9d88ef9b5a494f3914858bed89e0f94e412dfced')
install=${pkgname}.install

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    ./configure \
        --prefix=/usr \
        --libexecdir=/usr/lib/${pkgname} \
        --sysconfdir=/etc \
        --with-xscreensaverdir=/usr/share/xscreensaver/config \
        --with-xscreensaverhackdir=/usr/lib/xscreensaver \
        --with-mit-ext \
        --with-libnotify \
        --enable-locking \
        --disable-static
    make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" install
}
