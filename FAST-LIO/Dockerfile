FROM ros:noetic
ENV DEBIAN_FRONTEND=noninteractive
SHELL ["/bin/bash", "-c"]
RUN echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
RUN apt update
RUN apt install --no-install-recommends git ros-noetic-pcl-ros -y
RUN git clone https://github.com/Livox-SDK/Livox-SDK.git
RUN cd Livox-SDK/build && cmake .. && make && make install
RUN git clone https://github.com/Livox-SDK/livox_ros_driver.git catkin_ws/src
RUN source /opt/ros/noetic/setup.bash && cd catkin_ws && catkin_make
RUN cd catkin_ws/src && git clone https://github.com/hku-mars/FAST_LIO.git
RUN cd catkin_ws/src/FAST_LIO && git submodule update --init
RUN source /opt/ros/noetic/setup.bash && cd catkin_ws && catkin_make
RUN echo "source /catkin_ws/devel/setup.bash" >> ~/.bashrc