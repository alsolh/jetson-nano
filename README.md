# jetson-nano
guides for jetson nano

building yolo
clone
change below
GPU=1
CUDNN=1
OPENCV=1

best configuration for full yolo (3-4fps performance)
yolov3.cfg
change below lines
batch=1
subdivisions=1
width=220
height=220

command to run yolo demo in CSI connected camera like rpi

./darknet detector demo cfg/coco.data cfg/yolov3.cfg yolov3.weights "nvarguscamerasrc auto-exposure=1 ! video/x-raw(memory:NVMM), width=(int)1280, height=(int)720, format=(string)NV12, framerate=(fraction)60/1 ! nvvidconv flip-method=0 ! video/x-raw, width=(int)1280, height=(int)720, format=(string)BGRx ! videoconvert ! video/x-raw, format=(string)BGR ! appsink -e"
