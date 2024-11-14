# Maintainer: Your Name <youremail@example.com>
pkgname=tm-t88vi-driver-bin
pkgver=1.0
pkgrel=1
pkgdesc="Installs TM-T88VI drivers"
arch=('x86_64')
url="https://github.com/Snakehater/tm-t88vi-driver-bin" # TODO fix
license=('LicenseRef-EPSON')
depends=('libcups' 'gcc-libs' 'glibc')
source=("tmcupsbmptobin"
	"rastertotmt"
	"TM-T88VI.ppd"
	"LICENSE"
)
sha256sums=(
	'bb59f8655acd2b28e4ad29d6b0a69bed6c389a81114abaf77b1762eee8b869cb'
	'73d40ab3da2b708eaac109d9af1147fc45f4874c159b13c96daaa2c018ee3a04'
	'333ef3e6319b80bbabe2e19bec57651379f5a8c77cb0a224a5176df028ca42ff'
	'3500a6a38efa55e0943b2621a32b77c75376dc77aef1fd25fb32aae76538a754'
)

package() {
	install -Dm755 "${srcdir}/tmcupsbmptobin" "${pkgdir}/usr/bin/tmcupsbmptobin"
	install -Dm755 "${srcdir}/rastertotmt" "${pkgdir}/usr/lib/cups/filter/rastertotmt"
	install -Dm644 "${srcdir}/TM-T88VI.ppd" "${pkgdir}/etc/cups/ppd/TM-T88VI.ppd"
	install -Dm644 "${srcdir}/LICENSE" "${pkgdir}/usr/share/licenses/$pkgname/LICENSE"
	install -d "${pkgdir}/var/lib/tmt-cups"
}

post_install() {
	echo "==> Please restart CUPS with: sudo systemctl restart cups"
	echo "==> Connect the printer and add the printer to cups"
}
