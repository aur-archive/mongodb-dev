# Maintainer: Greg White <gwhite@kupulau.com> 

pkgname=mongodb-dev
pkgver=3.0.0.rc11
_mongorel=3.0.0-rc11
pkgrel=1
pkgdesc='MongoDB - development version'
arch=('x86_64')
url='http://www.mongodb.org'
license=('AGPL3')
depends=('pcre' 'snappy' 'openssl' 'gperftools' 'libsasl' 'boost-libs')
checkdepends=('python2-pymongo')
optdepends=('libpcap: needed for mongosniff')
provides=('mongodb')
conflicts=('mongodb')
backup=('etc/mongodb.conf')
install=mongodb.install
source=("https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-3.0.0-rc11.tgz"
        'mongodb.conf' 'mongodb.service')

package() {
  install -Dm644 "$srcdir/mongodb.conf" "$pkgdir/etc/mongodb.conf"
  install -Dm644 "$srcdir/mongodb.service" "$pkgdir/usr/lib/systemd/system/mongodb.service"
  install -dm700 -o mongodb -g daemon "$pkgdir/var/lib/mongodb"
  install -dm755 -o mongodb -g daemon "$pkgdir/var/log/mongodb"

  cp -r "$srcdir/mongodb-linux-x86_64-${_mongorel}/bin" "$pkgdir/usr"
}
md5sums=('d7c28860bb35e7e258a7e6978b6f4433'
         '4839fe1d638187ca3226e8267b947318'
         '96ab4517b48974ce0e566d9746a75a4f')
