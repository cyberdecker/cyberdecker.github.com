---
layout: post
title: "Installing OpenCV in Linux Mint"
description: ""
category: 
tags: [tutorial, opencv]
---
{% include JB/setup %}

My Linux Mint version is 14, but it could work for other versions.

Install the dependencies:

	sudo apt-get -y install build-essential checkinstall cmake pkg-config yasm libtiff4-dev libjpeg-dev libjasper-dev libavcodec-dev libavformat-dev  libswscale-dev libdc1394-22-dev libxine-dev libgstreamer0.10-dev libgstreamer-plugins-base0.10-dev libv4l-dev python-dev python-numpy libtbb-dev libqt4-dev  libgtk2.0-dev libfaac-dev libmp3lame-dev libopencore-amrnb-dev libopencore-amrwb-dev libtheora-dev libvorbis-dev libxvidcore-dev x264 v4l-utils ffmpeg

Download the latest OpenCV version here: <http://sourceforge.net/projects/opencvlibrary/files/opencv-unix/>.

Unzip the tar file:
	tar -xvf OpenCV-2.4.5.tar.gz

Do the following:
	cd opencv-2.4.5
	mkdir build
	cd build
	cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local -D WITH_TBB=ON -D BUILD_NEW_PYTHON_SUPPORT=ON -D WITH_V4L=ON -D INSTALL_C_EXAMPLES=ON -D INSTALL_PYTHON_EXAMPLES=ON -D BUILD_EXAMPLES=ON -D WITH_QT=ON -D WITH_OPENGL=ON ..
	make -j4
	sudo make install
	sudo sh -c 'echo "/usr/local/lib" > /etc/ld.so.conf.d/opencv.conf'
	sudo ldconfig

And you are ready! :)
