# Maintainer: Thomas Jost <schnouki@schnouki.net>
pkgname=python2-feedformatter
pkgver=0.4
pkgrel=4
pkgdesc="A Python library for generating news feeds in RSS and Atom formats"
url="http://code.google.com/p/feedformatter/"
arch=('any')
license=('BSD')
depends=('python2')
makedepends=('python2-setuptools')
source=(http://feedformatter.googlecode.com/files/feedformatter-$pkgver.tar.bz2)
md5sums=('9aefe618bc4a238940759050e0b97821')
sha1sums=('9798c8c26c3436aa0c7cb673f9f553e17474ea01')

build() {
  cd $srcdir/feedformatter-$pkgver
  python2 setup.py install --root=$pkgdir

  install -Dm644 COPYING $pkgdir/usr/share/licenses/$pkgname/COPYING

  # Patch to use python2
  find $pkgdir -type f \( -name '*.py' -or -executable \) -exec \
    sed -i -e "s|#![ ]*/usr/bin/python$|#!/usr/bin/python2|" \
           -e "s|#![ ]*/usr/bin/env python$|#!/usr/bin/env python2|" \
    \{\} +
}
