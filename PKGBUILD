# Created By Thief (escsunarcher@gmail.com)

pkgname=urtconnector-svn
pkgver=682
pkgrel=1
pkgdesc="Advanced UrbanTerror launcher program. Developed by members of russian clans =Xaoc=, Red*Army and Rus Devils Team. 
This program uses Qt4 and is written in C++."
arch=('i686' 'x86_64')
license=('GPL')
url="http://code.google.com/p/urtconnector"
depends=('qt>=4.6.2' 'qstat-svn')
makedepends=('pkgconfig' 'cmake>=2.6' 'subversion' 'boost' 'automoc4')
conflicts=('urtconnector')
provides=('urtconnector')
source=()
md5sums=()
_svntrunk=http://urtconnector.googlecode.com/svn/trunk/
_svnmod=urtconnector

build() {
svn co $_svntrunk $_svnmod
  msg "SVN checkout done or server timeout"
  msg "Starting make..."

  cd ${srcdir}/$_svnmod/src || return 1
  
  cmake -DCMAKE_INSTALL_PREFIX:PATH=/usr .. || return 1
  make || return 1
  make DESTDIR="$pkgdir" install || return 1
}
