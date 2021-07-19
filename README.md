# Automatic-Brain-Tumor-Detection-by-CenterNet-Based-Models

通过差分特征模块来优化centernet实现颅内肿瘤的自动检测

## 所需库： Tensorflow 1.13+Keras 2.1.5+Numpy+Matplotlib+Opencv+scipy

## 模型：通过残差差分特征模块替代ResNet50中的残差模块，并作为centernet的特征提取网络

## 训练过程自己的数据集

Step 1: 将数据集处理成VOC的格式，并将数据放置于VOCdevkit/VOC2007中

Step 2: 将model_data文件夹中的brain_classes.txt中的类别修改为自己数据集中的类别，并修改centernet_annotation.py中的第14行，将其改为自己数据集的类别

Step 2: 运行python voc2centernet.py，可以设置其中第24行的trainval_percent分配测试集

Step 3: 运行python voc_annotation.py

Step 4: 运行python train.py

Step 5: 修改centernet.py中第27行的模型路径并运行pyhton predict.py进行模型预测

训练过程如下：

![image](https://github.com/hzluyali/Automatic-Brain-Tumor-Detection-by-Centernet-Based-Models/blob/main/img/epoch_loss_2021_07_19_19_02_10.png)

## 直接根据预训练模型实现脑瘤的自动检测

预训练模型文件已被上传至百度云盘，链接为：

将模型文件拷贝至logs文件夹中，并修改centernet.py中第27行的模型路径，运行python predict.py

运行过程中，输入文件路径，如f:/1.jpg，按下enter键后就可获得检测结果，此外，按下n键再按下enter键后退出模型，效果如下

![image](https://github.com/hzluyali/Automatic-Brain-Tumor-Detection-by-Centernet-Based-Models/blob/main/img/788_result.jpg)

## 计算性能指标 (mAP)

修改centernet.py中第27行的模型路径并运行python get_dr_txt.py

运行python get_gt_txt.py

运行python get_map.py


