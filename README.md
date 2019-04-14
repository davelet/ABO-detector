# ABO-detector
A for Apple, B for Banana, O for Orange. 在mac上用tensorFlow的model训练苹果、香蕉、橘子识别器

## fruit-imanges目录
abo的图片和标记数据。

train目录是训练图片和标记，test是测试集。

## 工具

- xml_to_csv.py 用于将标记数据装换为csv文件
- generate_tfrecord.py 用于将csv文件转为tfrecord文件
- Object_detection_webcam.py 用于通过摄像头测试
