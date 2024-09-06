# Yolo_V3 (You only look once)

- yolo_v3的pytorch源码，含训练、推理、评测、部署脚本，论文传送门：

https://arxiv.org/abs/1506.02640 (v1)

https://arxiv.org/abs/1612.08242 (v2)

https://arxiv.org/abs/1804.02767 (v3)

## 数据集: VOC 
- **test**: (VOC2007, test) : 4952
- **train**: (VOC2007, trainval), (VOC2012, trainval) : 16553
- **CLASSES_NAMES**:

|             |          |         |           |           |
| :---------: | :------: | :-----: | :-------: | :-------: |
|  aeroplane  | bicycle  |  bird   |   boat    | bottle    |
|     bus     |   car    |  cat    |  chair    | cow       |
| diningtable |   dog    | horse   | motorbike | person    |
| pottedplant |  sheep   |  sofa   |  train    | tvmonitor |

- **官方网址** 

    http://host.robots.ox.ac.uk/pascal/VOC/voc2007/index.html
    
    http://host.robots.ox.ac.uk/pascal/VOC/voc2012/index.html


## 通用设置
|DataAugmentation    |
|:---:               |
|RandomSaturationHue |
|RandomContrast      |
|RandomBrightness    |
|RandomSampleCrop    |
|RandomExpand        |
|RandomHorizontalFlip|

|BS   |Pretrained|Epoch|Obj_loss|Cls_loss|Box_loss|NMS_th|Confidence|APT  |LearningRate|Lr_scheduler|
|:---:|:---:     |:---:|:---:   |:---:   |:---:   |:---: |:---:     |:---:|:---:       |:---:       |
|  64 |CoCo      |160  |1.0     | 1.0    | 5.0    |0.5   |0.3       |SGD  |0.01        |linear      |

## Results:
|TAG              |Size |mAP   |GFLOPs|Params|Pt_Size|FPS-3060|
|:---:            |:---:|:---: |:---: |:---: |:---:  |:---:   |
|Yolo_v3_Tiny     |512  |65.71%|  4.56|  2.39|  18.4M||
|Yolo_v3_Darknet53|512  |75.71%|133.40| 57.43|   442M||

<table>
<tr><th>Yolo_v3_Tiny</th> <th>Yolo_v3_Darknet53</th></tr>
<tr>
<td>
    
|ClassNames |AP   |
|--         |--   |
|aeroplane  |0.681|
|bicycle    |0.706|
|bird       |0.671|
|boat       |0.605|
|bottle     |0.370|
|bus        |0.755|
|car        |0.758|
|cat        |0.771|
|chair      |0.482|
|cow        |0.699|
|diningtable|0.637|
|dog        |0.729|
|horse      |0.766|
|motorbike  |0.740|
|person     |0.642|
|pottedplant|0.328|
|sheep      |0.602|
|sofa       |0.771|
|train      |0.753|
|tvmonitor  |0.677|
|mAP        |0.657|

</td>
<td>
    
|ClassNames |AP   |
|--         |--   |
|           |     |

</td>
</tr> 
</table>
