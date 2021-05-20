pkgname=usb-tethering
pkgver=0.2
pkgrel=1
pkgdesc="USB tethering on ConfigFS systems"
arch=('any')
url="https://gitlab.com/postmarketOS/pmaports/-/blob/master/main/postmarketos-mkinitfs/init_functions.sh"
license=('custom')
provides=()
depends=('systemd' 'dhcp')
options=()
source=('usb-tethering'
	'usb-tethering.service'
	'dhcpd.conf'
	'dhcpd4.service-customexec.conf'
	'tmpfiles.d.usb-tethering.conf')

package() {
  cd "${srcdir}"

  # usb tethering

  install -d ${pkgdir}/usr/lib/usb-tethering
  install -m 755 usb-tethering ${pkgdir}/usr/lib/usb-tethering

  install -d ${pkgdir}/usr/lib/systemd/system/
  install -m 644 usb-tethering.service ${pkgdir}/usr/lib/systemd/system/

  # dhcpd configuration

  install -d ${pkgdir}/usr/lib/tmpfiles.d/
  install -m 644 tmpfiles.d.usb-tethering.conf ${pkgdir}/usr/lib/tmpfiles.d/usb-tethering.conf

  install -d ${pkgdir}/etc/systemd/system/dhcpd4.service.d/
  install -m 644 dhcpd4.service-customexec.conf ${pkgdir}/etc/systemd/system/dhcpd4.service.d/customexec.conf

  install -d ${pkgdir}/etc/usb-tethering/
  install -m 644 dhcpd.conf ${pkgdir}/etc/usb-tethering/
}
md5sums=('e9dda426fe5ebae9b9f417e73488cbcd'
         'e64ec951b6b6dad6ea4680cab6ae48b5'
         '8d25b1c3f1146635800db77f300b908c'
         'd0e8b97346e8d4aeb106a412e3dd4c91'
         '138d916c252cea584e885323403c2c3a')
