# ApenPostV2.0
Numerical Simulation of Particle Mechanics and Post-processing Software Development Based on Discrete Element Method

# 离散元软件后处理程序 （ApenPost2.0）开发
***——复旦大学航空航天系本科毕业设计流体与生物力学组***
## 研究背景
1. 颗粒状是物质的一种基本形态，常见于工业生产和生活中，具有显著的非线性；
2. 离散元方法（Discrete Element Method, DEM）是一种重要的数值模拟仿真方法，在流体、固体力学和颗粒状物质力学中有着广泛的应用；
3. 本软件主要基于ApenDem和ApenPost1.0两款软件。离散元软件ApenDem由复旦大学航空航天系航空航天系黄骏副教开发（http://homepage.fudan.edu.cn/junhuang/)
；后处理程序ApenPost1.0由复旦大学航空航天系姚凯开发（专利登记号：2017SR644335）

## 代码说明
- 用python实现，基于openGL
- viewer.py建立Viewer类控制并管理整个程序的流程；
- scene.py建立场景类；
- 场景下的对象皆为节点，因此需要抽象出所有类型的对象的基类Node类，在node.py中建立；复杂的模型能够从简单的图元通过组合得到，组合后的模型也应该作为一个节点来看待。所以引入组合节点HierarchicalNode类，这是一个包含子节点的的节点，它将子节点存储在child_nodes中，同时作为Node的子类，它也必须实现render_self， 它的render_self函数就是简单地遍历调用子节点的render_self；
- primitive.py中抽象出了Primitive这个类，primitive又称作图元，是组成模型的基本单元，例如球体，立方体，三角等都属于图元。这些类的共通点在于它们的渲染都可以使用短小的OpenGL代码完成，同时对这些元素进行组合就可以组合出复杂的模型来；
- interaction.py实现用户接口；
- transformation.py实现能够平移或者改变节点大小的接口;
- trackball.py使用轨迹球算法来完成场景的旋转;

## TODO
1. 导入数据并可视化
2. 实现不同边界条件下的运动可视化
3. 完善用户交互界面

>Computer Graphics tutorial via shiyanlou（实验楼） https://www.shiyanlou.com/courses/561
