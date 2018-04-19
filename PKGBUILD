# Script generated with Bloom
pkgdesc="ROS - Messages, services and actions used by MoveIt"
url='http://moveit.ros.org'

pkgname='ros-lunar-moveit-msgs'
pkgver='0.9.1_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-lunar-actionlib-msgs'
'ros-lunar-catkin'
'ros-lunar-geometry-msgs'
'ros-lunar-message-generation'
'ros-lunar-object-recognition-msgs'
'ros-lunar-octomap-msgs'
'ros-lunar-sensor-msgs'
'ros-lunar-shape-msgs'
'ros-lunar-std-msgs'
'ros-lunar-trajectory-msgs'
)

depends=('ros-lunar-actionlib-msgs'
'ros-lunar-geometry-msgs'
'ros-lunar-message-runtime'
'ros-lunar-object-recognition-msgs'
'ros-lunar-octomap-msgs'
'ros-lunar-sensor-msgs'
'ros-lunar-shape-msgs'
'ros-lunar-std-msgs'
'ros-lunar-trajectory-msgs'
)

conflicts=()
replaces=()

_dir=moveit_msgs
source=()
md5sums=()

prepare() {
    cp -R $startdir/moveit_msgs $srcdir/moveit_msgs
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
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

