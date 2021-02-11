# Object-detection-using-Yolo-v3
Yolo is an algorithm that uses convolutional neural networks for object detection. In comparison to recognition algorithms, a detection algorithm does not only predict class labels but detects locations of objects as well.

## Extracting YOLO v3 weights:
Read_Weights class is used to extract the model weights from the "yolov3.weights" file into a suitable format that can be used for Keras. The class is also used to integrate the Darknet and YOLO architectures.

## Construction of the YOLO model:
conv_block is a function to create convolutional layers for CNN.
make_yolov3_model is a function to create layers of convolutional and stack together as a whole Yolo model (Since YOLO v3 uses darknet for feature extraction we will be constructing the model accordingly).
For feature extraction, Yolo uses Darknet-53 neural net pre-trained on ImageNet. Same as ResNet, Darknet-53 has shortcut (residual) connections, which help information from earlier layers flow further. We omit the last 3 layers (Avgpool, Connected, and Softmax) since we only need the features.

## Bounding Boxes:
BoundBox class is used to return object bounding box coordinates, object name and the threshold score.
decode_netout function is used to convert the prediction output into rectangle coordinates.
Non-Max Suppression (NMS) and Intersection over Union (IOU):
interval_overlap function is used to find the overlapping regions.
bbox_iou function is the implementation of IOU.
nms function is the implementation of NMS.
