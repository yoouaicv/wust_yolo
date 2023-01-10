# WUST_YOLO
`自封的，没有创新，啊哈哈哈哈`

<!--自封-->

### 项目介绍

受Yolov7的设计启发，将Yolov5的C3重新设计；在原ResBlock的{ 3×3conv 1×1conv }结构替换为{ 3×3conv_(c//2) 3×3conv(c) }结构，再将n个ResBlock的结果concat一起，与原C3结构连接。
下采样采取2×2avgpool与3×3conv(c * 2)组成。伴随着depth的扩大参数量与原Yolov5相比，略有增加。
<br>
`受设备限制，暂时测试WUST_YOLO-s的造作结果，后续有更新再上结果。`
<br>

### 实验结果

|   Model    | #Param. | FLOPs | Size | mAP<sup>val<br>0.5:0.95 | mAP<sup>val<br>0.5 |
| :--------: | :-----: | :---: | :--: | :-------: | :-------: |
| WUST_YOLO-N |  1.5M   |  4.1G | 640  |   31.2    |   48.5    |
| WUST_YOLO-S |  5.8M   | 14.8G | 640  |       |       |
| WUST_YOLO-M |  18.6M  | 46.5G | 640  |       |       |
| WUST_YOLO-L |  42.9M  |  107G | 640  |       |           |
| WUST_YOLO-X |  82.5M    |205.8G | 640  |           |           |

<br>

<br>

### 对比实验
`放这么多对比试验为了装逼的，没有别的作用`

|      Model       | #Param. | FLOPs  | Size | mAP<sup>val<br>0.5:0.95 | mAP<sup>val<br>0.5 |
| :--------------: | :-----: | :----: | :--: | :-------: | :-------: |
|     YOLOv5-N     |  1.9M   |  4.5G  | 640  |   28.0%   |           |
|    WUST_YOLO-N    |  1.5M   |  4.1G  | 640  |   **31.2%**   |           |
|     YOLOv5-S     |  7.2M   | 16.5G  | 640  |   37.4%   |           |
|     YOLOX-S      |  9.0M   | 26.8G  | 640  |   40.5%   |           |
|    PPYOLOE-S     |  7.9M   | 17.4G  | 640  |   42.7%   |           |
| YOLOV7-tiny-SiLU |  6.2M   | 13.8G  | 640  |   38.7%   |           |
|    WUST_YOLO-S    |  5.8M   | 14.8G  | 640  |      |           |
|     YOLOv5-M     |  21.2M  | 49.0G  | 640  |   45.4%   |           |
|     YOLOX-M      |  25.3M  | 73.8G  | 640  |   46.9%   |           |
|    PPYOLOE-M     |  23.4M  | 49.9G  | 640  |   48.6%   |           |
|      YOLOv7      |  36.9M  | 104.7G | 640  |   51.2%   |           |
|    WUST_YOLO-M    |  18.6M  | 46.5G  | 640  |           |           |
|     YOLOv5-L     |  46.5M  | 109.1G | 640  |   49.0%   |           |
|     YOLOX-L      |  54.2M  | 155.6G | 640  |   49.7%   |           |
|    PPYOLOE-L     |  52.2M  | 110.1G | 640  |   50.9%   |           |
|    WUST_YOLO-L    |  42.9M  |  107G  | 640  |           |           |
|     YOLOv5-X     |  86.7M  | 205.7G | 640  |   50.7%   |           |
|     YOLOX-X      |  99.1M  | 281.9G | 640  |   51.1%   |           |
|    PPYOLOE-X     |  98.4M  | 206.6G | 640  |   51.9%   |           |
|    WUST_YOLO-X    |  82.5M    |205.8G | 640  |      |           |

<br>

### 代码参考
`优秀的作品值得混合使用，刷一刷AP还是可以的，默认使用Yolov5的6.2版本代码训练`
* Yolov5  [https://github.com/ultralytics/yolov5](https://github.com/ultralytics/yolov5)
* Yolov6  [https://github.com/meituan/YOLOv6](https://github.com/meituan/YOLOv6)
* Yolov7  [https://github.com/WongKinYiu/yolov7](https://github.com/WongKinYiu/yolov7)
* PPYoloE  [https://github.com/PaddlePaddle/PaddleYOLO](https://github.com/PaddlePaddle/PaddleYOLO)
* PPYoloE-pytorch  [https://github.com/Nioolek/PPYOLOE_pytorch](https://github.com/Nioolek/PPYOLOE_pytorch)
* DAMO_YOLO  [https://github.com/tinyvision/damo-yolo](https://github.com/tinyvision/damo-yolo)
* YOLOX  [https://github.com/Megvii-BaseDetection/YOLOX](https://github.com/Megvii-BaseDetection/YOLOX)
* YOLOR  [https://github.com/WongKinYiu/yolor](https://github.com/WongKinYiu/yolor)

<br>
<br>
期待YOLOv8