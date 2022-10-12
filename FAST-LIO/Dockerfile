FROM ros:noetic
ENV DEBIAN_FRONTEND=noninteractive
RUN apt update
RUN apt install git -y
RUN git clone https://github.com/Livox-SDK/Livox-SDK.git
RUN cd Livox-SDK/build && cmake .. && make && make install
RUN git clone https://github.com/Livox-SDK/livox_ros_driver.git ws_livox/src
RUN apt install ros-noetic-pcl-ros -y
RUN cd ws_livox && catkin_make