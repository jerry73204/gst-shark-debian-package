# Maintainer: Your Name <youremail@domain.com>
pkgname=gst-shark
pkgver=0.8.1
pkgrel=1
pkgdesc="GstShark is a front-end for GStreamer traces"
arch=('amd64')
url="https://developer.ridgerun.com/wiki/index.php?title=GstShark"
license=('GPL')
depends=('libgstreamer1.0-dev' 'libgraphviz-dev' 'graphviz' 'octave' 'epstool' 'babeltrace' 'gtk-doc-tools')
makedepends=('git' 'meson' 'ninja-build')
source=('gst-shark::git+https://github.com/RidgeRun/gst-shark.git#tag=v0.8.1')
sha256sums=('SKIP')

# prepare() {
#     cd "$srcdir/${pkgname%-VCS}"
#     patch -p1 -i "$srcdir/${pkgname%-VCS}.patch"
# }

build() {
    cd "$srcdir/${pkgname}"
    meson builddir --prefix /usr/
    ninja -C builddir
}

# check() {
#     cd "$srcdir/${pkgname}"
# }

package() {
    cd "$srcdir/${pkgname}"
    DESTDIR="${pkgdir}" ninja install -C builddir
}
