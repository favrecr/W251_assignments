FROM ubuntu
# Set environments
#ENV ARCH=aarch64
ENV DEBIAN_FRONTEND=noninteractive

# Setup of drivers
RUN apt-get update
RUN apt-get install -y software-properties-common
RUN apt-get update && apt-get install -y \
    curl \
    git \
    python3.6 \
    python3-pip \
    python-opencv \
    python3-opencv \
    mosquitto \
    mosquitto-clients \
    vim \
    iputils-ping \
    libhdf5-dev \
    python3-numpy \
    python3-setuptools \
    python3-h5py \
    python3-wheel

RUN apt-get clean
EXPOSE 1883
RUN pip3 install paho-mqtt
RUN pip3 install ibm-cos-sdk
RUN pip3 install opencv-python

COPY cloud_forward_cos.py /
ENTRYPOINT python3 cloud_forward_cos.py