# build opencv 4 from scratch on ubuntu

## ubuntu 18.04 / Opencv 4.x

```sh
sudo apt -y install git gfortran
sudo apt -y install software-properties-common
sudo apt -y install libavcodec-dev libavformat-dev libswscale-dev libdc1394-22-dev
cd /usr/include/linux
sudo ln -s -f ../libv4l1-videodev.h videodev.h
sudo apt -y install libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev
sudo apt -y install libgtk2.0-dev libtbb-dev qt5-default
sudo apt -y install libfaac-dev libmp3lame-dev libtheora-dev
sudo apt -y install libopencore-amrnb-dev libopencore-amrwb-dev
sudo apt -y install x264 v4l-utils
sudo apt -y install libgoogle-glog-dev libgflags-dev
sudo apt -y install python3-dev python3-pip
sudo apt -y install python3-testresources
sudo apt install build-essential cmake git pkg-config libgtk-3-dev     libavcodec-dev libavformat-dev libswscale-dev libv4l-dev     libxvidcore-dev libx264-dev libjpeg-dev libpng-dev libtiff-dev     gfortran openexr libatlas-base-dev python3-dev python3-numpy     libtbb2 libtbb-dev libdc1394-22-dev

sudo apt install libopenblas-dev libopenblas-base
sudo apt install liblapacke-dev
sudo ln -s /usr/include/lapacke.h /usr/include/x86_64-linux-gnu # corrected path for the library 
export Open_BLAS_INCLUDE_SEARCH_PATHS=/usr/include/x86_64-linux-gnu
export Open_BLAS_LIB_SEARCH_PATHS=/usr/lib/x86_64-linux-gnu
sudo apt install liblapacke-dev
python3 -c "import cv2; print(cv2.__version__)"
cmake -D CMAKE_BUILD_TYPE=RELEASE     -D CMAKE_INSTALL_PREFIX=/usr/local     -D INSTALL_C_EXAMPLES=ON     -D INSTALL_PYTHON_EXAMPLES=ON     -D OPENCV_GENERATE_PKGCONFIG=ON    -D BUILD_EXAMPLES=ON -D OPENCV_EXTRA_MODULES_PATH='/home/forward/Downloads/opencv_contrib-4.5.0/modules' -DPYTHON_INCLUDE_DIR=$(python3 -c "from distutils.sysconfig import get_python_inc; print(get_python_inc())")  -DPYTHON_LIBRARY=$(python3 -c "import distutils.sysconfig as sysconfig; print(sysconfig.get_config_var('LIBDIR'))") ..

```


```sh

sudo apt install python3-opencv
python3 -c "import cv2; print(cv2.__version__)"

sudo apt install build-essential cmake git pkg-config libgtk-3-dev \
    libavcodec-dev libavformat-dev libswscale-dev libv4l-dev \
    libxvidcore-dev libx264-dev libjpeg-dev libpng-dev libtiff-dev \
    gfortran openexr libatlas-base-dev python3-dev python3-numpy \
    libtbb2 libtbb-dev libdc1394-22-dev
    
cmake -D CMAKE_BUILD_TYPE=RELEASE \
    -D CMAKE_INSTALL_PREFIX=/usr/local \
    -D INSTALL_C_EXAMPLES=ON \
    -D INSTALL_PYTHON_EXAMPLES=ON \
    -D OPENCV_GENERATE_PKGCONFIG=ON \
    -D OPENCV_EXTRA_MODULES_PATH=~/opencv_build/opencv_contrib/modules \
    -D BUILD_EXAMPLES=ON ..
    
pkg-config --modversion opencv4
python3 -c "import cv2; print(cv2.__version__)"

```
