 # Maintainer: DarkXero <info@techxero.com>

pkgname=grub-hooks
pkgdesc="Fixes, additions and enhancements to grub and os-prober."
pkgver=3.7
pkgrel=1
arch=('any')
license=('GPL')
depends=(coreutils efibootmgr gawk grep grub lsb-release)
optdepends=(os-prober)
backup=('etc/install-grub.conf')
replaces=("grub-tools")

url=https://github.com/xerolinuxDev/$pkgname
_url="https://raw.githubusercontent.com/xerolinuxDev/$pkgname/main"

source=(
  $_url/grub-install.hook
  $_url/grub-kernel.hook
  $_url/grub-update.hook
  $_url/reboot-checker.hook
  $_url/reboot-check
  $_url/reboot-notify
  $_url/grub-auto
)

package() {
  cd $srcdir

  install -d $pkgdir/usr/share/libalpm/hooks
  echo "Install grub-hooks"
  install -Dm644 grub-install.hook     $pkgdir/usr/share/libalpm/hooks/grub-install.hook
  install -Dm644 grub-kernel.hook      $pkgdir/usr/share/libalpm/hooks/grub-kernel.hook
  install -Dm644 grub-update.hook      $pkgdir/usr/share/libalpm/hooks/grub-update.hook
  install -Dm644 reboot-checker.hook    $pkgdir/usr/share/libalpm/hooks/reboot-checker.hook
  echo "Install reboot-scripts"
  install -Dm755 reboot-check     $pkgdir/usr/local/bin/reboot-check
  install -Dm755 reboot-notify    $pkgdir/usr/local/bin/reboot-notify
  install -Dm755 grub-auto        $pkgdir/usr/local/bin/grub-auto

}
