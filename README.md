# 水下声学目标检测数据集

## 数据集简介
本数据集来源于鹏城实验室推出的水下声学目标检测赛项，是当前业内最大、最具广泛性的声学图像数据集之一，适用于前视声呐图像目标检测相关研究。数据集包含多种水下目标的声呐图像及对应标注信息，可用于训练和评估目标检测算法在水下声学场景中的性能。




## 数据内容

### 目标类别
共包含8类水下目标，分别为：
- 规则几何结构物体：正方体（cube）、球体（ball）、圆柱体（cylinder）
- 其他水下物体：人体模型（human body）、轮胎（tyre）、圆形地笼（circle cage）、方形地笼（square cage）、铁桶（metal bucket）


### 数据集构成
| 数据类型       | 数量       | 格式及内容                                                                 |
|----------------|------------|--------------------------------------------------------------------------|
| 训练集         | 4000张     | 含.bmp格式前视声呐图像文件及对应的.xml格式标注文件（包含目标检测框参数及类别） |
| 初赛A榜测试集  | 1000张     | 含.bmp格式声呐图像及.xml格式声呐参数信息文件（无标注结果）                 |
| 初赛B榜测试集  | 1000张     | 含.bmp格式声呐图像及.xml格式声呐参数信息文件（无标注结果）                 |
| 提交样例文件   | 1个        | sample_submission.csv（供参考的提交格式样例）                             |


### 数据说明
1. 采集设备：Tritech Gemini 1200i 前视声呐
2. 图像特性：声呐图像为二维矩阵形式的原始回声强度信息，存储为3通道.bmp格式，实际处理时使用单通道数据即可
3. 预处理建议：原始图像未经增益调整，直接显示接近全黑，建议进行直方图均衡化以提升可视化效果（不强制要求，对算法设计影响较小）
4. 标注格式：标注文件为.xml格式，包含声呐工作参数（类型、版本、量程、水平/垂直开角等）、图像尺寸及目标信息（类别、检测框坐标），具体格式如下：
   ```xml
   <?xml version"1.0" encoding="UTF-8"?>
   <annotation>
       <sonar>
           <type>声呐类型</type>
           <version>声纳版本号</version>
           <range>声呐量程</range>
           <horiangle>声呐水平开角</horiangle> 
           <vertiangle>声纳垂直开角</vertiangled> 
           <soundspeed>声速</soundspeed>
           <frequency>频率</frequency>
       </sonar>
       <folder>所在文件夹名称</folder> 
       <filenane>文件名</filenane>
       <path>文件绝对路径</path>
       <size>
           <width>宽度</width>
           <height>高度</height>
           <depth>深度</depth>
       </sizes>
       <object>
           <name>标注类别</name> 
           <bndbox>
               <xmin>左上角x坐标</xmin> 
               <ymin>左上角y坐标</ymin>
               <xmax>右下角x坐标</xmax>   
               <ymax>右下角y坐标</ymax>
           </bndbox>
       </object>
   </annotation>

## 下载地址:

[Sonor_dataset](https://pan.baidu.com/s/157t15PczW9q4pYAFtsHkmQ)  
密码:fvm8
