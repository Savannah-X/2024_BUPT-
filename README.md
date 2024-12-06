# 2024_BUPT-
2024BUPT医学影像实验
第三次.基于CT重建的计算机模拟实验
##一、实验目的
理解 CT 重建的基本原理，包括投影数据的获取和图像重建算法。
通过模拟实验，对比不同重建算法的性能，如重建图像的质量、计算效率等。
##二、实验原理
CT 重建基于物体对 X 射线的衰减特性。从不同角度获取物体的投影数据，然后利用重建算法还原出物体内部的密度分布图像。
常用的重建算法有滤波反投影算法（FBP）和迭代重建算法等。
##三、实验步骤
###1.生成模拟物体模型（20分）
在二维平面上，创建Shepp-Logan phantom，用矩阵表示物体的密度分布，每个像素点的值代表该点的密度。

###2.模拟 X 射线投影数据获取（30分）
选择一定数量的投影角度（如 0° - 180°，每隔 1° 或 2° 取一个角度）。
对于每个投影角度，计算 X 射线穿过物体模型时的衰减情况，得到投影数据。这可以通过对物体模型中沿 X 射线传播路径上的像素密度进行积分（模拟 X 射线的衰减过程）来实现。
例如，使用 Radon 变换（SciPy 库中的 radon 函数）来获取投影数据。

###3.重建算法实现（30分）
1）基于滤波反投影的方法
对获取的投影数据进行滤波处理，常用的滤波器有 Ram - Lak 滤波器、Shepp - Logan 滤波器等。
然后将滤波后的投影数据进行反投影，将各个角度的投影信息还原到图像空间，得到重建图像。
2）基于代数重建技术 ART的方法
初始化一个重建图像（通常为全零矩阵或具有一定初始猜测值的矩阵）。
对于每个投影角度，根据投影数据和当前重建图像计算误差，然后更新重建图像，重复多次迭代过程，直到满足收敛条件（如重建图像的变化小于一定阈值）。

###4.结果评估与比较（20分）
计算重建图像与原始物体模型之间的误差指标，如均方误差（MSE）、峰值信噪比（PSNR）等并绘制误差曲线。
通过可视化对比原始物体模型、不同算法重建的图像，观察图像的清晰度、伪影情况等

##四、实验总结
分析不同算法的优缺点，讨论投影数据质量、算法复杂度等因素对重建结果的影响。

##五、补充材料
###1. MATLAB实现shepp-Logan头模型X-CT图像重建过程：https://www.jianshu.com/p/b53aab73642e
###2.代数重建算法步骤：
![image](https://github.com/user-attachments/assets/ab97f929-196c-4cff-a7c1-8851c99d703a)














