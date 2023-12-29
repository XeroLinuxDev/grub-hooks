# Maintainer: DarkXero <info@techxero.com>

pkgname=grub-hooks
pkgdesc="Fixes, additions and enhancements to grub and os-prober."
pkgver=1.0.1
pkgrel=1
arch=('any')
license=('GPL')
depends=(coreutils efibootmgr gawk grep grub lsb-release xero-hooks)
optdepends=(os-prober)
backup=('etc/install-grub.conf')
replaces=("grub-tools")

url=https://github.com/xerolinux/$pkgname
_url="https://raw.githubusercontent.com/xerolinux/$pkgname/main"

source=(
  $_url/install-grub
  $_url/install-grub.conf
  $_url/grub-install.hook
  $_url/grub-kernel.hook
  $_url/grub-update.hook
)

package() {
  cd $srcdir

  install -d $pkgdir/usr/share/libalpm/hooks
  echo "Install install-grub"
  install -Dm755 install-grub          $pkgdir/usr/bin/install-grub
  echo "Install install-grub.conf"
  install -Dm644 install-grub.conf     ${pkgdir}/etc/install-grub.conf
  echo "Install grub-hooks"
  install -Dm644 grub-install.hook     $pkgdir/usr/share/libalpm/hooks/grub-install.hook
  install -Dm644 grub-kernel.hook      $pkgdir/usr/share/libalpm/hooks/grub-kernel.hook
  install -Dm644 grub-update.hook      $pkgdir/usr/share/libalpm/hooks/grub-update.hook

}
