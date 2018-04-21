# Script generated with Bloom
pkgdesc="ROS - The hector_worldmodel stack helps to collect and fuse information about objects in the world. It is used by Team Hector Darmstadt to localize victims and QR codes in the Robocup Rescue scenario. See <a href="http://wiki.ros.org/hector_object_tracker">hector_object_tracker</a> for further details."
url='http://ros.org/wiki/hector_worldmodel'

pkgname='ros-kinetic-hector-worldmodel'
pkgver='0.3.4_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
)

depends=('ros-kinetic-hector-object-tracker'
'ros-kinetic-hector-worldmodel-geotiff-plugins'
'ros-kinetic-hector-worldmodel-msgs'
)

conflicts=()
replaces=()

_dir=hector_worldmodel
source=()
md5sums=()

prepare() {
    cp -R $startdir/hector_worldmodel $srcdir/hector_worldmodel
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

