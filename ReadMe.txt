基于深度学习网络的模型匹配算法研究  
A Survey of  Shape Matches Based on Deep Learning NetWork

本实验将三维模型输入到自编码器函数映射网络（AutoEncoder Functional Maps Network,AEFMNet）中，经过训练测试评估得到最终模型匹配结果，并用MATLAB对其处理得到可视化结果。

源代码：https://github.com/maning666/homework
配置环境：
CUDA 10
TensorFlow 1.13
Python 3.7

数据集：采用SURREAL数据集作为训练集训练神经网络，该数据集是一个大规模的合成人体模型，结合真实人体模型和姿态学习的SMPL模型来保证各种人体体型的自然姿态的真实度。
数据集下载地址：https://nuage.lix.polytechnique.fr/index.php/s/LJFXrsTG22wYCXx

数据预处理：
选取SURREAL数据集中前5000个三角网格模型进行数据预处理，利用解压后的MATLAB_Tool文件夹的.m文件处理数据集，
重新网格化将包含顶点信息和面片信息的off模型转换成对应几何特征信息的mat类型的数据用于训练，保存在<null/spectral>文件夹里。

训练：
运行python train.py，结果保存在<results>文件夹。

测试：
运行python test.py，结果保存在<test>文件夹。

评估：
运行<eval_scripts>文件夹的python eval_faust.py文件，结果保存在<matches>文件夹。
可视化结果：将评估后的.mat文件利用<maprecovery-code>文件夹的demo.m获得模型匹配可视化结果。
