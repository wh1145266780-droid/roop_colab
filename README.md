# RoopColab
使用谷歌免费的GPU在线运行一键换脸, 可以进行图片换脸，视频换脸。手机电脑都可以通过网页运行。


Roop

[![打开](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/dream80/roop_colab/blob/main/roop_v1.3.1.ipynb)


FaceFusion

[![打开](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/dream80/roop_colab/blob/main/tonyff_last.ipynb)


## 图片换脸
![demo](4.jpg)   

## 视频换脸
![demo](cmp.gif)  

# 更新  
250819
- 修复完全不能使用的问题
- 剔除烦人NSFW限制，和无用的TF依赖
- 修复GPU加速问题，换脸器提速x10
- 优化模型下载逻辑，减少重复下载，节省流量和时间


![demo](new.jpg)   

# 使用方法

直接点击 【open in colab】 ，根据笔记本提示一步一步运行即可，熟练之后设置好素材，可以一键运行，详细的使用教程，点[这里](https://www.tonyisstark.com/1240.html) 


在托尼大大来之前，我们可以采取以下临时的解决方案：

Colab 降级到3.10
```
# Example: install Python 3.10
!sudo apt-get update -y
!sudo apt-get install python3.10 python3.10-distutils -y
!sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.10 1
!sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.12 2
!sudo update-alternatives --config python3
```


# Make pip work with the new Python
!curl -sS https://bootstrap.pypa.io/get-pip.py | python3
安装依赖那里改成如下：

#@title 3.安装依赖
#有红色警告不用担心！
%cd /content/roop_colab/roop/

!pip install -r requirements.txt
!pip install torch==2.0.1+cu118 torchvision==0.15.2+cu118 --index-url https://download.pytorch.org/whl/cu118
!pip install onnxruntime-gpu==1.22.0
# install system packages
!sudo apt-get update -y
!sudo apt-get install -y python3-tk tk

# install Python packages
!pip install customtkinter==5.2.0 tkinterdnd2==0.3.0

run.py 文件开头添加
import os
os.environ.pop("MPLBACKEND", None)
os.environ["MPLBACKEND"] = "Agg"

