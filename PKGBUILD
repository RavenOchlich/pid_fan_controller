# Maintainer: tmikey

_reponame=pid_fan_controller
pkgname=pid-fan-controller
pkgver=1.2
pkgrel=1
pkgdesc="PID fan controller with Python3 and NVIDIA gpu support"
arch=('any')
url="https://github.com/RavenOchlich/pid_fan_controller"
license=('GPL3')
depends=('python3' 'python-simple-pid' 'python-pyaml')
provides=("$pkgname")
source=("git+https://github.com/RavenOchlich/pid_fan_controller.git")
md5sums=('SKIP')
backup=('etc/pid_fan_controller_config.yaml')

package() {
  cd "$_reponame"
  install -m 644 -Dt "$pkgdir/usr/lib/systemd/system/" \
    pid-fan-controller.service \
    pid-fan-controller-sleep-hook.service \
    set-manual-fan-speed@.service
  install -m 644 -Dt "$pkgdir/etc/" pid_fan_controller_config.yaml
  install -m 755 -Dt "$pkgdir/usr/share/$pkgname/" \
    main_loop.py \
    pid_fan_controller.py \
    override_auto_fan_control.py \
    set_manual_fan_speed.py
}

# vim:set ts=2 sw=2 et:
