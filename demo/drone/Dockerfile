FROM wangso/python3-opencv-ffmpeg:V1
RUN apt-get -y update && apt-get -y install software-properties-common apt-utils python3-pip python3-dev libopencv-dev python3-opencv build-essential ffmpeg unzip nano curl git wget iproute2 iperf net-tools
RUN pip3 install cmake flask flask_restful scikit-build opencv_contrib_python numpy requests
WORKDIR /
ADD https://api.github.com/repos/zachs18/zerotrust/git/refs/heads/demo-v1 version.json
RUN git clone https://github.com/zachs18/zerotrust.git
WORKDIR /zerotrust
RUN git checkout demo-v1
WORKDIR /zerotrust/demo/drone
RUN mkdir output
ENTRYPOINT ["python3", "drone.py"]
