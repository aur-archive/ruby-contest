# Maintainer: Jochen Schalanda <jochen+aur@schalanda.name>
# Contributor: "David Campbell <davekong@archlinux.us>"
_gemname=contest
pkgname=ruby-$_gemname
pkgver=0.1.3
pkgrel=2
pkgdesc='Write more readable tests in Test::Unit with this tiny script.'
arch=(any)
url='http://github.com/citrusbyte/contest'
license=('MIT')
depends=('ruby')
source=(https://rubygems.org/downloads/$_gemname-$pkgver.gem)
noextract=($_gemname-$pkgver.gem)
md5sums=('3cdd786cfb051e176855eee40679968a')

package() {
  cd "$srcdir"
  # _gemdir is defined inside package() because if ruby[gems] is not installed on
  # the system, makepkg will exit with an error when sourcing the PKGBUILD.
  local _gemdir="$(ruby -rubygems -e'puts Gem.default_dir')"

  gem install --no-user-install --ignore-dependencies -i "$pkgdir$_gemdir" \
    -n "$pkgdir/usr/bin" "$_gemname-$pkgver.gem"
}
# vim:set ts=2 sw=2 et:
