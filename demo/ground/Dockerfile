FROM wangso/python3-opencv-ffmpeg:V1
RUN wget https://mizzouceri-s3.s3.amazonaws.com/yolo_weights.zip
RUN unzip yolo_weights.zip
ADD https://api.github.com/repos/zachs18/zerotrust/git/refs/heads/demo-v1 version.json
RUN git clone https://github.com/zachs18/zerotrust
WORKDIR /zerotrust
RUN git checkout demo-v1
WORKDIR /zerotrust/demo/ground
RUN mkdir YOLO output
RUN cp /yolo-object-detection/yolo-coco/yolov3.weights ./YOLO/
RUN cp /yolo-object-detection/yolo-coco/yolov3.cfg ./YOLO/
RUN cp /yolo-object-detection/yolo-coco/coco.names ./YOLO/
RUN rm -r /yolo-object-detection/ /yolo_weights.zip
ENTRYPOINT ["python3", "ground.py"]
