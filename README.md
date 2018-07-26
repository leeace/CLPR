# Chinese License Plate Recognition

### 介绍
这些代码是用于参加2018智慧城市技术挑战赛车牌识别任务，主要工作是基于深度学习完成的。
针对功能评测图像库中的车牌，采用由粗糙到精细的三层定位方法获得准确的车牌图像再输入到OCR模型中进行识别。
针对性能评测图像库中的车牌，采用检测角点再进行图像处理之后输入到OCR模型中进行识别。

### Python 依赖

+ Python 3.6
+ Keras (>2.0.0)
+ Tensorflow(>1.5.x)
+ Numpy (>1.10)
+ Scipy (0.19.1)
+ OpenCV(>3.0)
+ Scikit-image (0.13.0)
+ PIL


### 模型说明

+ cascade.xml  初步的车牌定位检测模型
+ model12.h5 左右边界回归模型
+ ocr_plate_all_gru.h5 基于GRU的序列模型，对车牌进行精确定位
+ plate_type.h5 用于车牌颜色判断的模型
+ weights_densenet_use_1.h5 用于识别功能评测图像库中的车牌的OCR模型
+ weights_densenet_use_2.h5 用于识别性能评测图像库中的车牌的OCR模型

### 算法流程

### 代码使用

运行如下代码即可对测试集图片进行测试：
''' python inference.py --gpu_id 0 --dataroot {dataroot} '''

其中，gpu_id为使用的GPU序号，dataroot为测试集数据的根目录。
