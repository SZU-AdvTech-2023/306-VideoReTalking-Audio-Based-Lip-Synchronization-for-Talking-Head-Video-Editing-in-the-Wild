D-net训练.ipynb保存了video-retalking项目的D-net训练代码。由于源代码没提供模型训练的代码，所以我根据论文中的描述写的trainer.同时简化了一下loss函数，可能存在与文章有偏差的地方，若有错误请指出！

## 准备
#### 1.环境
```
conda create -n video_retalking python=3.8
conda activate video_retalking
conda install ffmpeg

# 安装torch和torchvision，最好是gpu版本。同时安装一下包：
basicsr==1.4.2
kornia==0.5.1
face-alignment==1.3.4
ninja==1.10.2.3
einops==0.4.1
facexlib==0.2.5
librosa==0.9.2
dlib==19.24.0
gradio>=3.7.0
numpy==1.23.4
```
#### 2.D-net依赖的模型文件
```
expression.mat
face3d_pretrain_epoch_20.pth
shape_predictor_68_face_landmarks.dat
# 请自行下载模型文件到./checkpoints中
```
#### 3.数据集
由于D-net是逐帧处理所以可以提供任意图片集为训练集，不仅限于视频集。


