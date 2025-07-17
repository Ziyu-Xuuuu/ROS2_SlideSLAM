FROM ros:noetic

ENV DEBIAN_FRONTEND=noninteractive

# 基础环境
RUN apt-get update -o Acquire::Check-Valid-Until=false \
 && apt-get update -o Acquire::Check-Date=false \
 && apt-get install -y \
    tzdata sudo curl git wget nano cmake build-essential \
    python3-pip python3-rosdep python3-vcstool \
    libdw-dev libgoogle-glog-dev libfmt-dev \
    ros-noetic-catkin ros-noetic-ros-numpy \
    ros-noetic-pcl-ros ros-noetic-tf ros-noetic-tf2-ros \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*


# Python dependencies
RUN pip3 install \
    numpy==1.22.3 \
    scikit-learn \
    scipy \
    matplotlib \
    open3d \
    git+https://github.com/dimatura/pypcd.git \
    ultralytics==8.0.59

# 建立工作区
WORKDIR /root/slideslam_ws
RUN mkdir -p src

CMD ["bash"]

