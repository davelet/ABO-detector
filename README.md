# ABO-detector
A for Apple, B for Banana, O for Orange. 在mac上用tensorFlow的model训练苹果、香蕉、橘子识别器。

训练环境和方法请看[TensorFlow-Object-Detection-API-Tutorial-Train-Multiple-Objects-On-Macos](https://github.com/davelet/TensorFlow-Object-Detection-API-Tutorial-Train-Multiple-Objects-On-Macos)。

## fruit-imanges目录
abo的图片和标记数据。

train目录是训练图片和标记，test是测试集。

## 工具

- xml_to_csv.py 用于将标记数据装换为csv文件
- generate_tfrecord.py 用于将csv文件转为tfrecord文件
- Object_detection_webcam.py 用于通过摄像头测试

## 训练（使用特定模型）
在object_detection目录下执行
> python model_main.py \
    --pipeline_config_path=/Users/sheldon/pythonProjects/py3venv/kaggle/faster_rcnn_inception_v2_pets.config \
    --model_dir=/Users/sheldon/pythonProjects/py3venv/kaggle/fruit-images \
    --alsologtostderr

## 导出图
在object_detection目录下执行
> python export_inference_graph.py --input_type image_tensor --pipeline_config_path /Users/sheldon/pythonProjects/py3venv/kaggle/faster_rcnn_inception_v2_pets.config --trained_checkpoint_prefix /Users/sheldon/pythonProjects/py3venv/kaggle/fruit-images/model.ckpt-2132 --output_directory /Users/sheldon/pythonProjects/py3venv/kaggle/fruit-images/graph

## 测试
在object_detection目录下执行
> python /Users/sheldon/pythonProjects/ABO-detector/Object_detection_webcam.py

## 转换
在tensorflow目录下执行`bazel build tensorflow/tools/graph_transforms:summarize_graph`

## 资料

[电子书教程](https://github.com/davelet/ABO-detector/edit/master/objectdetection_in_tensorflowdemo.pdf)

[TensorFlow lite Object detection](https://www.tensorflow.org/lite/models/object_detection/overview)

[对象识别](https://www.tensorflow.org/lite/models/object_detection/overview#customize_model)

[图片分类](https://www.tensorflow.org/lite/models/image_classification/overview)

[模型转到移动端](https://www.tensorflow.org/lite/convert/python_api)

https://github.com/nnsuite/nnstreamer/wiki/%5BTF-Lite%5D-How-to-Convert-Tensorflow-Model-to-TF-Lite-Model

https://www.quantumobile.com/mobile-object-detector-with-tensorflow-lite/

[ensorFlow Lite 概述和模型转化简介](https://zhuanlan.zhihu.com/p/37941205)

[TensorFlow Lite(1/3)：编译](https://zhuanlan.zhihu.com/p/32190069)

[TensorFlow Lite的量化工具](https://zhuanlan.zhihu.com/p/45213001)

[Android端的Tensorflow部署](https://github.com/dingjikerbo/Android-DeepLearning/blob/master/doc/Android%E7%AB%AF%E7%9A%84Tensorflow%E9%83%A8%E7%BD%B2%E4%B8%80.md)

[pre-train using slim](https://github.com/priya-dwivedi/Deep-Learning/tree/master/soccer_area_of_action/slim)
