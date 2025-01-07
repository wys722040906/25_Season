##### 登录

- **SSH** 远程连接到一台服务器并执行一系列任务

```
ssh workshop@47.238.35.119 -p 50047
Password: workshop
su workshop #切换用户
passwd#修改密码
qazwsx123

#vscode
Ctrl+Shift+P
Remote-SSH: Connect to Host... 
Add New SSH Host...
```

仔细阅读README.md文件，实现README.md中的要求



##### 嵌入式

- 脉冲测频
- 指定频率脉冲输出
- 模拟电压输入检测
- E2PROM工作参数存储
- 串口通信
- 按键实现界面切换与控制
- LCD LED显示 -- 电压 脉冲频率



##### windows适用vscode

- cmd

```
where code
doskey code="C:\Users\wys\AppData\Local\Programs\Microsoft VS Code\bin\code.cmd"
```

- powershell

```
//临时
Set-Alias code "C:\Users\wys\AppData\Local\Programs\Microsoft VS Code\bin\code.cmd"
Get-Alias code
//永久
notepad.exe $PROFILE
Set-Alias code "C:\Users\wys\AppData\Local\Programs\Microsoft VS Code\bin\code.cmd"
```



# 单目相机

## 运动补偿

过估计相机和物体的相对运动，可以对图像进行对齐和补偿，使篮球在图像中保持清晰，从而改善物体检测的效果

## 残影去除

去残影算法（如基于时序的运动去模糊技术）来清理图像中的运动残影。常见的方法包括基于时间序列的背景建模或利用光流估计对残影区域进行修正。通过去除残影，可以增强目标检测框的准确性，使篮球的检测框更加准确

- 提高快门速度
- 深度学习建模

深度学习模型（如FlowNet、PWC-Net等）能够通过训练对复杂的运动场景（包括高速运动和残影）进行更有效的建模

- 残影去除与深度增强

结合运动模糊的去除技术，如基于神经网络的图像去模糊方法（例如，DeblurGAN），可以减少残影效应，提升光流计算的精度，从而有助于提高深度估计的准确性。





## 光流深度估计

利用光流技术估计图像中物体的运动矢量，可以用来推测篮球的运动轨迹。通过对图像序列中的光流场进行分析，可以获取更精确的位置信息，进而进行深度估计。光流法不直接依赖于静态尺寸，而是通过物体在图像中的运动来推断物体的速度和位置。

**基于光流的深度估计**：结合光流估计，可以通过相机的相对运动和物体的速度来推算物体的深度。这种方法不需要精准的物体尺寸，可以根据篮球的运动信息来估算距离。

## 深度学习

有效地弥补由于残影产生的检测框不准确问题

**MonoDepth、MiDaS**

Mask R-CNN、YOLOv4

部分深度学习模型（如3D YOLO）结合了空间和时间信息，可以从运动视频中估算物体的深度和三维位置

## 物理模型

抛物线或带阻力的抛物线模型







