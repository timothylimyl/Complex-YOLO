# Purpose

The purpose of the repository is to gain an understanding of Complex-YOLO and try it out for myself for the purpose of my Final Year Project (FYP). The code repository was taken from [Deepak Ghimire](https://github.com/ghimiredhikura/Complex-YOLOv3). I have investigated the details of the algorithms and reported it here (and in my FYP). Some extra test was also done to gain more insights. Visualisation of Complex-YOLO inference on KITTI Dataset (12 images stitch together):

<p align="center"><img src="https://github.com/timothylimyl/Complex-YOLO/blob/main/visualization/inference.gif" ></p>


# Complex-YOLO (Details)





# Extra Test/Insight

Point Cloud data can be very sparse + Complex-YOLO takes everything from the bird eye view and just push to the ground. Thus, we can guess that it will do very poorly with objects such as Pedestrian and Cyclist once we increase the IoU:

mAP (0.75 IoU):

| Model/Class             | Car     | Pedestrian | Cyclist | Average |
| ----------------------- |:--------|:-----------|:--------|:--------|
| Complex-YOLO-v3         | 91.66   |    9.0     |  24.37  |  41.7   |


Besides that, I added a COCO style object detection metric as it is a good indication of performance:

COCO (IOU [.50: .05: .95]):

| Model/Class             | Car     | Pedestrian | Cyclist | Average |
| ----------------------- |:--------|:-----------|:--------|:--------|
| Complex-YOLO-v3         |70.92    | 31.67      | 42.48   | 48.35   |


I plan to get a few different object detection algorithms and test the difference using the COCO Metric. I believe that algorithms that is more robust, the performance will not degrade badly when a more stringent metric is used.
