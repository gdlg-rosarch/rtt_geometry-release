# Script generated with Bloom
pkgdesc="ROS - This metapackage contains tools for integrating the Orocos Kinematics and Dynamics Library (KDL) with the Orocos Toolchain and Real-Time Toolkit (RTT)."
url='http://www.orocos.org/'

pkgname='ros-kinetic-rtt-geometry'
pkgver='2.9.1_1'
pkgrel=1
arch=('any')
license=('LGPL'
)

makedepends=('ros-kinetic-catkin'
)

depends=('ros-kinetic-eigen-typekit'
'ros-kinetic-kdl-typekit'
)

conflicts=()
replaces=()

_dir=rtt_geometry
source=()
md5sums=()

prepare() {
    cp -R $startdir/rtt_geometry $srcdir/rtt_geometry
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

