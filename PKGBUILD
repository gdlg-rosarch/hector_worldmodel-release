# Script generated with Bloom
pkgdesc="ROS - hector_object_tracker is the core package of hector_worldmodel. It listens to percept message from detectors (e.g. heat signatures of persons or recognitions of other objects of interest in the scene) and fuses all information to a single worldmodel state. Objects will be tracked over time and their states can be influenced by a couple of services. The percept to object association problem is solved either automatically based on the Mahalanobis distance, or a unique object_id can be given in the percept message. If a hector_nav_msgs/GetDistanceToObstacle service is available, the object_tracker can optionally deduce the depth of objects in the scene by projection to the nearest obstacle (wall)."
url='http://ros.org/wiki/hector_object_tracker'

pkgname='ros-kinetic-hector-object-tracker'
pkgver='0.3.4_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-hector-marker-drawing'
'ros-kinetic-hector-nav-msgs'
'ros-kinetic-hector-worldmodel-msgs'
'ros-kinetic-image-geometry'
'ros-kinetic-roscpp'
'ros-kinetic-tf'
)

depends=('ros-kinetic-hector-marker-drawing'
'ros-kinetic-hector-nav-msgs'
'ros-kinetic-hector-worldmodel-msgs'
'ros-kinetic-image-geometry'
'ros-kinetic-roscpp'
'ros-kinetic-tf'
)

conflicts=()
replaces=()

_dir=hector_object_tracker
source=()
md5sums=()

prepare() {
    cp -R $startdir/hector_object_tracker $srcdir/hector_object_tracker
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

