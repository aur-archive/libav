pkgname=libav
pkgver=11
pkgrel=1
pkgdesc="Open source audio and video processing tools forked from ffmpeg"
arch=('i686' 'x86_64')
url="http://www.libav.org/"
license=('LGPL')
depends=('alsa-lib' 'bzip2' 'libtheora' 'libvpx' 'x264' 'xvidcore' 'faac' 'lame' 'opus' 'libvorbis' 'freetype2' 'gnutls' 'openssl' 'rtmpdump')
makedepends=('yasm')
provides=('ffmpeg')
conflicts=('ffmpeg')


source=(http://libav.org/releases/$pkgname-$pkgver.tar.xz)

build() {
  cd "$srcdir/$pkgname-$pkgver"
  ./configure --prefix=/usr --enable-shared --disable-static --disable-debug --enable-gpl --enable-nonfree \
    --enable-libtheora  --enable-libvpx --enable-libx264 --enable-libxvid \
    --enable-libfaac --enable-libmp3lame --enable-libopus --enable-libvorbis \
    --enable-libfreetype --enable-gnutls --enable-openssl --enable-librtmp --enable-x11grab
  make
  make doc/av{play,probe,conv}.1
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make DESTDIR="$pkgdir/" install install-man
}

# vim:set ts=2 sw=2 et:
md5sums=('bfc894b3a2747212c2f48a38a468a15e')
