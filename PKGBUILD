# Script generated with Bloom
pkgdesc="ROS - hector_worldmodel_msgs is a message package to comes with the hector_worldmodel stack. The messages can be used to send percepts from images (hector_worldmodel_msgs/ImagePercept) or other sources (hector_worldmodel_msgs/PosePercept) to the hector_object_tracker node. The tracker publishes model updates as hector_worldmodel_msgs/Object messages and latches the whole model state as a hector_worldmodel_msgs/ObjectModel message."
url='http://ros.org/wiki/hector_worldmodel_msgs'

pkgname='ros-kinetic-hector-worldmodel-msgs'
pkgver='0.3.4_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-geometry-msgs'
'ros-kinetic-message-generation'
'ros-kinetic-sensor-msgs'
)

depends=('ros-kinetic-geometry-msgs'
'ros-kinetic-message-runtime'
'ros-kinetic-sensor-msgs'
)

conflicts=()
replaces=()

_dir=hector_worldmodel_msgs
source=()
md5sums=()

prepare() {
    cp -R $startdir/hector_worldmodel_msgs $srcdir/hector_worldmodel_msgs
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

