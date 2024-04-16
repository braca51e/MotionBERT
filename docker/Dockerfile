FROM nvidia/cuda:11.6.1-devel-ubuntu20.04

#get deps
RUN apt-get update && \
DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
python3-dev python3-pip python3-setuptools git g++ wget make libtiff-dev \
libprotobuf-dev protobuf-compiler libopencv-dev \
libgoogle-glog-dev libboost-all-dev libhdf5-dev libatlas-base-dev \
libfreetype-dev libfreetype6 libfreetype6-dev

#for python api
RUN pip3 install --upgrade pip
RUN pip3 install numpy opencv-python 
COPY ../requirements.txt /requirements.txt
RUN pip3 install -r requirements.txt
RUN rm requirements.txt

#Copy artifacts
COPY ../models/best_epoch.bin /motionBert/models/best_epoch.bin

#get openpose
WORKDIR /motionBert


