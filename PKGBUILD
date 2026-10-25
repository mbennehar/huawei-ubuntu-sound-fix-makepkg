# Maintainer: mouss <mouss@localhost>
pkgname=huawei-ubuntu-sound-fix
pkgver=1.3.1
pkgrel=1
pkgdesc="Daemon fixing headphone and speaker switching for Huawei MateBook laptops"
arch=('any')
url="https://github.com/Smoren/huawei-ubuntu-sound-fix"
license=('custom')
depends=('bash' 'alsa-utils' 'alsa-tools' 'procps-ng')
makedepends=('git')
install="${pkgname}.install"
_commit="9f1990ec612616f2073fe732880aaf2fd4f5f9c4"
source=("${pkgname}::git+${url}.git#commit=${_commit}")
md5sums=('SKIP')

prepare() {
  cd "${srcdir}/${pkgname}"

  # Ensure scripts locate files relative to their own directory
  sed -i '2i cd "$(dirname "$0")"' install.sh
  sed -i '2i cd "$(dirname "$0")"' uninstall.sh

  # Prevent pacman DB lock error when install.sh is invoked during pacman transaction
  sed -i 's|sudo pacman -Sy alsa-tools alsa-utils --noconfirm|pacman -Q alsa-tools alsa-utils \&>/dev/null \|\| sudo pacman -Sy alsa-tools alsa-utils --noconfirm|' install.sh

  # Make install.sh and uninstall.sh directly accessible under src/
  ln -sf "${pkgname}/install.sh" "${srcdir}/install.sh"
  ln -sf "${pkgname}/uninstall.sh" "${srcdir}/uninstall.sh"
}

package() {
  cd "${srcdir}/${pkgname}"
  install -d "${pkgdir}/opt/${pkgname}"
  find . -mindepth 1 -maxdepth 1 ! -name '.git' -exec cp -r -t "${pkgdir}/opt/${pkgname}" {} +
}
