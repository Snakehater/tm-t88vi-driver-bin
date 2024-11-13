# Maintainer: Your Name <youremail@example.com>
pkgname=tm-t88vi-driver
pkgver=1.0
pkgrel=1
pkgdesc="Installs TM-T88VI drivers"
arch=('x86_64')
license=('none')
source=("tmcupsbmptobin"
	"rastertotmt"
	"TM-T88VI.ppd")
sha256sums=(
	'bb59f8655acd2b28e4ad29d6b0a69bed6c389a81114abaf77b1762eee8b869cb'
	'73d40ab3da2b708eaac109d9af1147fc45f4874c159b13c96daaa2c018ee3a04'
	'333ef3e6319b80bbabe2e19bec57651379f5a8c77cb0a224a5176df028ca42ff')

package() {
	install -Dm755 "${srcdir}/tmcupsbmptobin" "${pkgdir}/usr/bin/tmcupsbmptobin"
	install -Dm755 "${srcdir}/rastertotmt" "${pkgdir}/usr/lib/cups/filter/rastertotmt"
	install -Dm644 "${srcdir}/TM-T88VI.ppd" "${pkgdir}/etc/cups/ppd/TM-T88VI.ppd"
	install -d "$/var/lib/tmt-cups"
}
