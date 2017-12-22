# Maintainer: Savino Jossi <savino.jossi@gmail.com>

_pkgname=scientifica
pkgname=${_pkgname}-font
pkgver=1.0.0
pkgrel=1
pkgdesc='Tall and condensed bitmap font for geeks.'
arch=(any)
url=http://sourceforge.net/projects/terminus-font/
depends=(xorg-fonts-encodings xorg-fonts-alias xorg-font-utils fontconfig)
conflicts=(scientifica-font)
provides=(scientifica-font)
install=scientifica-font.install
source=(https://raw.githubusercontent.com/sjossi/scientifica/master/75-yes-scientifica.conf
        https://raw.githubusercontent.com/NerdyPepper/scientifica/master/scientifica-11.bdf)
md5sums=('527aa5ed9023e7d2face57d48cfce034'
         'd134dfeeb97109ce3b582d3c89341035')

build()
{
cat <<EOF > 75-yes-scientifica.conf
<?xml version="1.0"?>
<!DOCTYPE fontconfig SYSTEM "fonts.dtd">
<fontconfig>
<!-- Accept scientifica font -->
  <selectfont>
    <acceptfont>
      <pattern>
        <patelt name="family"><string>scientifica</string></patelt>
      </pattern>
    </acceptfont>
  </selectfont>
</fontconfig>
EOF
}

package()
{
  install -Dm644 75-yes-scientifica.conf "${pkgdir}/etc/fonts/conf.avail/75-yes-scientifica.conf"
  install -dm755 "${pkgdir}/etc/fonts/conf.d"
  ln -sf -t "${pkgdir}/etc/fonts/conf.d" ../conf.avail/75-yes-terminus.conf
}
