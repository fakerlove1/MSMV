# 🦕MSMV:基于多尺度和多视图Transformer的半监督医学图像分割框架

> Official PyTorch implementation of "MSMV: Semi-Supervised Medical Image Framework Segmentation based on Multi-Scale and Multi-View Transformer"

## 🛠️ 安装 

如果这是一个pip的安装环境，请运行以下命令

~~~bash
pip install -r requirements.txt
~~~

如果这是一个conda环境，请运行以下命令

~~~bash
conda env create -f requirements.yml
~~~



## ✨ 数据集

| DataSets | Downloadlink                                         |
| -------- | ---------------------------------------------------- |
| ACDC     | https://www.kaggle.com/datasets/jokerak/acdch5       |
| LIDC     | https://www.kaggle.com/datasets/jokerak/lidcidri     |
| ISIC     | https://www.kaggle.com/datasets/jokerak/isic2018-224 |



## ⭐训练

`step 1`: 下载代码并准备运行环境

1. 下载代码。
2. 确保已安装 Anaconda 或 Miniconda。
3. 运行 `pip install -r requirement.txt` 进行环境初始化。

`step 2`: 下载数据集

`step 3`: 使用 MSMV 进行实验非常方便。例如，如果您想运行 Mean-Teacher 算法：

1. Modify the config file in `config/mean_teacher_unet_30k_224x224_ACDC.yaml` as you need

   ~~~yaml
   # Dataset Configuration
   datasets: "acdc" # Dataset name
   num_classes: 4 # Number of categories
   data_path: "/home/ubuntu/data/ACDC" # Dataset placement location
   save_path: "checkpoint/2023-02-26-mean_teacher-ACDC" # Code Save Location
   name: "mean_teacher-ACDC"
   ckpt: None # Pre-training weight position
   cuda: True # Whether to use GPU
   ~~~

2. Run `python 2017_03_NIPS_Mean-Teacher_ACDC.py`

如果您想运行论文项目，请直接运行以下代码

~~~python
python main.py
~~~

## 🏷️支持其他算法

目前，我们已经实现了 7 种流行的半监督医学图像分割算法。

| Date    | Name         | Title                                                        | Reference |
| ------- | ------------ | ------------------------------------------------------------ | --------- |
| 2017-03 | Mean-Teacher | [Mean teachers are better role models: Weight-averaged consistency targets improve semi-supervised deep learning results](https://arxiv.org/abs/1703.01780) | NeurlPS   |
| 2019-07 | UAMT         | [Uncertainty-aware Self-ensembling Model for Semi-supervised 3D Left Atrium Segmentation](https://arxiv.org/abs/1907.07034) | MICCAI    |
| 2021-06 | CPS          | [Semi-Supervised Semantic Segmentation with Cross Pseudo Supervision](https://arxiv.org/abs/2106.01226) | CVPR      |
| 2021-12 | CTCT         | [Semi-Supervised Medical Image Segmentation via Cross Teaching between CNN and Transformer](https://arxiv.org/abs/2112.0489) | MIDL      |
| 2022-02 | ICT-MegSeg   | [AN EMBARRASSINGLY SIMPLE CONSISTENCY REGULARIZATION METHOD FOR SEMI-SUPERVISED MEDICAL IMAGE SEGMENTATION](https://arxiv.org/abs/2202.00677) | ISBI      |
| 2022-03 | SSNet        | [Exploring Smoothness and Class-Separation for Semi-supervised Medical Image Segmentation](https://arxiv.org/abs/2203.01324v3) | MICCAI    |
| 2022-08 | S4CVNet      | [When CNN Meet with ViT: Towards Semi-Supervised Learning for Multi-Class Medical Image Semantic Segmentation](https://arxiv.org/abs/2208.06449) | CVPR      |



## ♥️ 鸣谢

我们的模型与 [SSL4MIS](https://github.com/HiLab-git/SSL4MIS) 相关。感谢他们的出色工作！