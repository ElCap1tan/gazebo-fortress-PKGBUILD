# Maintainer: Yannic Wehner <yannic.wehner@gmail.com>
pkgname=gazebo-fortress
pkgver=1.0.3
pkgrel=1
pkgdesc="A multi-robot simulator for outdoor environments"
url="https://gazebosim.org/"
arch=('any')
license=('Apache')
depends=(
    'curl'
    'freeglut'
    'ffmpeg'
    'benchmark'
    'eigen'
    'freeimage'
    'gflags'
    'glew'
    'gts'
    'jsoncpp'
    'ogre-1.9'
    'protobuf'
    'python3'
    'sqlite'
    'tinyxml2'
    'urdfdom'
    'libwebsockets'
    'libxi'
    'libxml2'
    'libxmu'
    'libyaml'
    'libzip'
    'zeromq'
    'python-distutils-extra'
    'python-psutil'
    'pybind11'
    'python-pytest'
    'python-yaml'
    'qt5-charts'
    'qt5-graphicaleffects'
    'qt5-declarative'
    'qt5-quickcontrols'
    'qt5-quickcontrols2'
    'qt5-location'
    'qt5-base'
    'rubocop'
    'ruby'
    'swig'
    'uuid'
    'xorg-server-xvfb'
)
makedepends=(
    'cmake'
    'git'
    'python-vcstools'
    'python-colcon-common-extensions'
    'lsb-release'
    'gnupg'
)
source=(
    "$pkgname-$pkgver.yaml::https://raw.githubusercontent.com/ignition-tooling/gazebodistro/master/collection-fortress.yaml"
)
sha256sums=(
    'SKIP'
)
# install=ros2-humble.install

prepare() {
    echo prepare
    # Clone the repos
    mkdir -p $srcdir/src
    vcs import $srcdir/src < $srcdir/$pkgname-$pkgver.yaml
}

build() {
    colcon build --merge-install
}

package() {
    mkdir -p $pkgdir/opt/gazebo/fortress
    cp -r $srcdir/install/* $pkgdir/opt/gazebo/fortress/
}
