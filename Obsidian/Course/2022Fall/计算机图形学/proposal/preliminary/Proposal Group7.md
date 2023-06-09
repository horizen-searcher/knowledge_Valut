## Group member
吴俊成
任柯睿
马嘉
孙睿
姜垒
王子安
## Motivation
在当前的CG技术中，PBR技术与光线追踪技术，分别在渲染贴近真实的复杂材质以及模拟复杂反射折射方面取得了较为良好的成果。因此我们希望将这两项技术应用于计算机图形学中最为简单的物体：球体，依托台球室场景进行组合交互，动态展现物体在运动时的渲染效果。我们希望借助这个项目，直观认识两个技术优势的同时，理解光线追踪与传统流水线渲染方式之间的异同，同时提升图形学变成水平以及较复杂项目的设计实现水平。
## The goal of the project
1.展示较为逼真的台球室全局场景。
2.使用PBR技术让物体表面更加符合物理实际。
3.借助物理引擎实现台球击打和碰撞。
4.使用光追技术实现较为真实的光照效果。
5.良好的人机交互体验。
## The scope of the project
* 球体自旋
	球体在加塞击打的情况下会有一个自旋的运动，而这一运动将更加复杂，同时提升碰撞检测时的计算难度。另外，在光追渲染的时候，对其自旋运动的渲染可能也会添加难度（要让人感受出它的自旋以及自旋方向）
## Related CG techniques
### PBR
* PBR
	* 光的反射与漫反射
	*  微平面模型
	* BRDF双向反射分布函数
*  PBR材质
	* 金属度和粗糙度
	* 菲涅尔函数
	* 法线分布函数
	* 几何函数
### 光线追踪
* 光线求交 
* 蒙特卡洛采样 
* BVH： 
	* BV（Bounding Volume）是包含⼀组物体的空间体，它⽐其所包含的⼏何物体形状要简单的多，所以对 它进⾏碰撞检测速度⽐直接与物体本身求相交更快。常⻅的包围体有轴对⻬包围盒、球体包围盒、 OBB。 
	* BVH是⼀种以物体BV为基础进⾏划分的结构。它由根节点、内部节点和叶⼦节点组成。其中叶⼦节点存 放物体，每个⾮叶⼦节点都有包围体，⽗节点可以把⼦节点包围起来。 
	* BRDF：BRDF（Bidirectional Reflectance Distribution Function，双向反射分布函数）是真实感图形学 中最核⼼的概念之⼀，它描述的是物体表⾯将光能从任何⼀个⼊射⽅向反射到任何⼀个视点⽅向的反射特 性，即⼊射光线经过某个表⾯反射后如何在各个出射⽅向上分布。BRDF模型是绝⼤多数图形学算法中⽤ 于描述光反射现象的基本模型。
	* 低差异序列与重要性采样来加速光线追踪的收敛
### 物理引擎
* 摩擦力
球体在球桌上运动，会由于与台球桌的摩擦力而损失速度。因此一个合理的摩擦力是必要的，它能让球的运动看起来更加自然。
* 动量守恒&能量守恒
	球体和球体、球体和球桌的碰撞（刚体碰撞），都会导致球体改变运动方向、改变速度大小，而碰撞的过程是遵循动量守恒和能量守恒的（假设碰撞时间极短、同时该时刻外力可以忽略）。因此可以通过此来对球体的碰撞进行检测和计算。
* 多球碰撞
	球体的碰撞并不是一对一，可能存在多颗球互相碰撞的情形，而这时发生碰撞的系统无法单纯使用两个物体碰撞的动量守恒和能量守恒来计算。
* 物理引擎：
	* Bullet物理引擎可以实现三维碰撞检测和计算，有离散和连续碰撞检测功能的刚体模拟的支持，可以支持我们对3D小球的碰撞检测和计算。
	* Box2D物理引擎可以实现在二维空间上的碰撞，其相对于Bullet来说更加简单易用，对于所有球，它们的碰撞都只发生在球心平面上，因此其实是个二维碰撞，使用Box2D完全可以实现。
## Implementation plan
* 第10周：
	* 相关储备知识的学习
* 第11周：
	* 搭建基础的场景
* 第12周：
	* 搭建基础的场景
	* 基础场景中添加交互
	* PBR的学习与准备
	* 光线追踪的学习与准备
* 第13周：
	*  基础场景中添加交互
	* PBR的初步实现
	* 光线追踪的初步实现
* 第14周：
	* PBR的实现
	* 光线追踪的实现
* 第15周：
	* 汇总调试
## Roles in group
* 光线追踪
	* 姜垒
	* 王子安
	* 孙睿
* PBR
	* 吴俊成
	* 任柯睿
* 物理引擎
	* 马嘉