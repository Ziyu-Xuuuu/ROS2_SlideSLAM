FROM ros:humble

ENV DEBIAN_FRONTEND=noninteractive

# 安装基础依赖
RUN apt-get update -o Acquire::Check-Valid-Until=false \
 && apt-get update -o Acquire::Check-Date=false \
 && apt-get install -y \
    tzdata sudo curl git wget nano cmake build-essential \
    python3-pip python3-vcstool python3-colcon-common-extensions \
    libdw-dev libgoogle-glog-dev libfmt-dev \
    ros-humble-pcl-conversions ros-humble-tf2 ros-humble-tf2-ros \
    ros-humble-tf-transformations ros-humble-rclpy \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

# 安装 Python 依赖
RUN pip3 install \
    numpy==1.22.3 \
    scikit-learn \
    scipy \
    matplotlib \
    open3d \
    git+https://github.com/dimatura/pypcd.git \
    ultralytics==8.0.59

# 创建 ROS2 工作空间
WORKDIR /root/slideslam_ros2_ws
RUN mkdir -p src

# 默认进入 bash（手动 colcon build）
CMD ["bash"]

