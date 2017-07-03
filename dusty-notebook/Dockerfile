FROM jupyter/scipy-notebook

MAINTAINER Dusty Argyle <dustymargyle@gmail.com> 

USER $NB_USER

# Install Python 3 Tensorflow
RUN conda install --quiet --yes 'tensorflow=1.0*'

# Install Python 2 Tensorflow
RUN conda install --quiet --yes -n python2 'tensorflow=1.0*'

# Installs
USER root
RUN apt-get update && apt-get install -y \
    wget \
    tree \
    build-essential \
    cmake \
    git \
    unzip \
    pkg-config \
    python-dev \
    python-opencv \
    libopencv-dev \
    libav-tools  \
    libjpeg-dev \
    libpng-dev \
    libtiff-dev \
    libjasper-dev \
    libgtk2.0-dev \
    python-numpy \
    python-pycurl \
    libatlas-base-dev \
    gfortran \
    webp \
    python-opencv \
    qt5-default \
    libvtk6-dev \
    zlib1g-dev \
    cmake \
    llvm

#RUN mkdir -p ~/opencv cd ~/opencv && \
#    wget https://github.com/Itseez/opencv/archive/3.0.0.zip && \
#    unzip 3.0.0.zip && \
#    rm 3.0.0.zip && \
#    mv opencv-3.0.0 OpenCV && \
#    cd OpenCV && \
#    mkdir build && \
#    cd build && \
#    cmake \
#    -DWITH_QT=ON \
#    -DWITH_OPENGL=ON \
#    -DFORCE_VTK=ON \
#    -DWITH_TBB=ON \
#    -DWITH_GDAL=ON \
#    -DWITH_XINE=ON \
#    -DBUILD_EXAMPLES=ON .. && \
#    ldconfig

RUN mkdir -p ~/opencv cd ~/opencv && \
    wget https://github.com/opencv/opencv/archive/3.2.0.zip && \
    unzip 3.2.0.zip && \
    rm 3.2.0.zip && \
    mv opencv-3.2.0 OpenCV && \
    cd OpenCV && \
    mkdir build && \
    cd build && \
    cmake \
    -DWITH_QT=ON \
    -DWITH_OPENGL=ON \
    -DFORCE_VTK=ON \
    -DWITH_TBB=ON \
    -DWITH_GDAL=ON \
    -DWITH_XINE=ON \
    -DBUILD_EXAMPLES=ON .. && \
    ldconfig

RUN conda install -c conda-forge -y jupyter_contrib_nbextensions

EXPOSE 8888
USER root
ENV GRANT_SUDO=yes
ENV GEN_CERT=yes
ENV UID=1000
ENV GID=1000
