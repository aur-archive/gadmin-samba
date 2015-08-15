# $Id: PKGBUILD 40911 2011-03-01 14:49:33Z andrea $
# Maintainer: Barton Cline <barton bcdesignswell com>
# Contributor: Marcin Kaczorek <kaczus@karek.pl>

pkgname=gadmin-samba
pkgver=0.3.4
pkgrel=1
pkgdesc="An easy to use GTK+ frontend for the SAMBA file and print server"
url="http://dalalven.dtdns.net/linux/gadmintools-webpage/"
arch=('i686' 'x86_64')
license=('GPL')
depends=('gtk2' 'samba')
optdepends=("gksu: Graphical Su Support")
replaces=('gsambad')
install=gadmin-samba.install
#http://dalalven.dtdns.net/linux/gadmin-samba/gadmin-samba-0.3.4.tar.gz
source=("http://dalalven.dtdns.net/linux/${pkgname}/${pkgname}-${pkgver}.tar.gz" "${pkgname}.desktop" "${pkgname}-menu")
options=(!emptydirs)

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  ./configure --prefix=/usr --sysconfdir=/etc \
  --localstatedir=/var --sbindir=/usr/sbin
  make
}
package() {
	cd ${srcdir}/${pkgname}-${pkgver}
    make DESTDIR=${pkgdir} install
    install -d ${pkgdir}/usr/share/applications/
	install -Dm755 ${srcdir}/${pkgname}-menu ${pkgdir}/usr/bin/${pkgname}-menu
    install -Dm644 ${srcdir}/${pkgname}.desktop ${pkgdir}/usr/share/applications/${pkgname}.desktop
}
md5sums=('4bb40adbca6ae46de1b5e394065efc5a'
         '6ac291dbd55b3f2176a29a32f8f546a2'
         '47a9d6a57bf44ba3d55d63de35c8223c')
