# Script generated with Bloom
pkgdesc="ROS - Cost maps, following the style of ethz-asl's grid_map library."


pkgname='ros-kinetic-cost-map-ros'
pkgver='0.3.3_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('boost'
'opencv'
'ros-kinetic-catkin'
'ros-kinetic-cost-map-core'
'ros-kinetic-cost-map-msgs'
'ros-kinetic-costmap-2d'
'ros-kinetic-ecl-build'
'ros-kinetic-ecl-command-line'
'ros-kinetic-ecl-console'
'ros-kinetic-grid-map-core'
'ros-kinetic-grid-map-costmap-2d'
'ros-kinetic-grid-map-ros'
'ros-kinetic-grid-map-visualization'
'ros-kinetic-nav-msgs'
'ros-kinetic-roslib'
'yaml-cpp'
)

depends=('boost'
'opencv'
'ros-kinetic-cost-map-core'
'ros-kinetic-cost-map-msgs'
'ros-kinetic-costmap-2d'
'ros-kinetic-ecl-build'
'ros-kinetic-ecl-command-line'
'ros-kinetic-ecl-console'
'ros-kinetic-grid-map-core'
'ros-kinetic-grid-map-costmap-2d'
'ros-kinetic-grid-map-ros'
'ros-kinetic-grid-map-visualization'
'ros-kinetic-nav-msgs'
'ros-kinetic-roslib'
'yaml-cpp'
)

conflicts=()
replaces=()

_dir=cost_map_ros
source=()
md5sums=()

prepare() {
    cp -R $startdir/cost_map_ros $srcdir/cost_map_ros
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

