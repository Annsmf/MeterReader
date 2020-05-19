# MeterReader

## 系统方案

第一步使用目标检测算法检测待识别表具区域，第二步使用语义分割算法分割出表具的刻度和指针，第三步计算表具读数。

* 目标检测<br>
  平衡考虑算法的推理速度和检测效果，目标检测算法采用YOLOv3模型实现。目标检测部分只做检测不对表具进行分类。 

* 语义分割<br>
  根据目标检测的结果，从原图中裁剪出表具区域图像，做为语意分割模型的输入，考虑到刻度和指针均为细小区域，采用分割效果较好的DeepLapv3+模型实现。 

* 读数计算<br>
  预先配置表具相关数据（单位、量程等），结合语意分割结果计算出表具最终读数。
