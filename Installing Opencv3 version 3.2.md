
### Installing OpenCV with CUDA support
#### Install dependencies

Update apt-get

     sudo apt-get update

Install dependencies

         sudo apt-get install -y build-essential cmake git
         sudo apt-get install -y pkg-config unzip ffmpeg qtbase5-dev 
         sudo apt-get install -y python-dev python3-dev python-numpy python3-numpy
         sudo apt-get install -y libopencv-dev libgtk-3-dev libdc1394-22 libdc1394-22-dev 
         sudo apt-get install -y libjpeg-dev libpng12-dev libtiff5-dev libjasper-dev
         sudo apt-get install -y libavcodec-dev libavformat-dev libswscale-dev 
         sudo apt-get install -y libxine2-dev libgstreamer0.10-dev libgstreamer-plugins-base0.10-dev
         sudo apt-get install -y libv4l-dev libtbb-dev libfaac-dev libmp3lame-dev 
         sudo apt-get install -y libopencore-amrnb-dev libopencore-amrwb-dev libtheora-dev
         sudo apt-get install -y libvorbis-dev libxvidcore-dev v4l-utils python-vtk
         sudo apt-get install -y liblapacke-dev libopenblas-dev checkinstall
         sudo apt-get install -y libgdal-dev

Download OpenCV and OpenCV's extra modules

        cd ~
        wget -O opencv.zip https://github.com/Itseez/opencv/archive/3.2.0.zip

unzip opencv.zip

        wget -O opencv_contrib.zip https://github.com/Itseez/opencv_contrib/archive/3.2.0.zip
        unzip opencv_contrib.zip

Create directory to house build files

        cd opencv
        mkdir build
        cd build/

#### Build

Use cmake to configure the build.

        cmake -D CMAKE_BUILD_TYPE=RELEASE \
        -D CMAKE_INSTALL_PREFIX=/usr/local \
        -D FORCE_VTK=ON \
        -D WITH_TBB=ON \
        -D WITH_V4L=ON \
        -D WITH_QT=ON \
        -D WITH_OPENGL=ON \
        -D WITH_CUDA=ON \
        -D ENABLE_FAST_MATH=1 \
        -D CUDA_FAST_MATH=1 \
        -D WITH_CUBLAS=ON \
        -D CUDA_NVCC_FLAGS="-D_FORCE_INLINES" \
        -D OPENCV_EXTRA_MODULES_PATH=~/opencv_contrib/modules \
        -D WITH_GDAL=ON \
        -D WITH_XINE=ON \
        -D INSTALL_PYTHON_EXAMPLES=ON \
        -D INSTALL_C_EXAMPLES=OFF \
        -D BUILD_EXAMPLES=ON ..

Make sure the log says

            Use CUFFT: YES
            Use CUBLAS: YES
            Use fast math: YES

in the Nvidia cuda section

Check that your CMake command exited without error and compile OpenCV:

        make -j8

### Installation

Run the following commands to install OpenCV

        sudo make install
        sudo /bin/bash -c 'echo "/usr/local/lib" > /etc/ld.so.conf.d/opencv.conf'
        sudo ldconfig
        sudo apt-get update

And reboot your computer

Check installation

In [2]:

        import cv2

In [3]:

        cv2.__version__

Out[3]:

        '3.2.0'

