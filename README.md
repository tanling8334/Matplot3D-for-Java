# Matplot3D for Java



Matplot3D for JAVA是一个基于JAVA SE 1.5环境开发的三维图形图表组件。以jar包的方式存在。超轻量级设计实现，jar文件大小不超过200KB。内含自主研发的三维几何造型、绘制算法，不依托图形硬件，不依托OpenGL、DriectX、JAVA 3D等基础库，纯JAVA语言软件实现，可以非常方便的将Matplotlib 3D for JAVA(V2.0)显示面板嵌入到自己JAVA GUI程序中。

本组件提供简单的外观API，可以方便生成三维效果的图形图表。支持鼠标等输入设备交互式操作，可方便的缩放和改变观察角度。V2.0版本全面显示支持动态编程，可实时生成三维模型动态改变动画。

作者email : ta8334@126.com   ;   QQ : 17746302

       Matplot3D for JAVA是一个基于JAVA  SE  1.5环境开发的三维图形图表组件。以jar包的方式存在。内含自主研发三维造型算法引擎，轻量级（jar不超过200k），不依赖硬件纯JAVA实现。 它提供易于使用的API，可以方便的生成3维效果的各种图形图表。
        此组件、开发工具可用于大数据的可视化和数学分析等领域。


![TEST](http://github.com/tanling8334/Matplot3D-for-Java/raw/master/pic/Earth.gif "Earth.gif")  

![三维热力、等高](https://images.gitee.com/uploads/images/2019/0911/100114_e64861fb_1658632.gif "dgrl_small.gif")  
    ---------------------------------------------------------  
![动态曲面](https://images.gitee.com/uploads/images/2019/0911/100216_72059ffe_1658632.gif "wave.gif")  
    ---------------------------------------------------------  
![输入图片说明](https://images.gitee.com/uploads/images/2019/0912/153145_68f71a4e_1658632.gif "hsqm_.gif")  
    ---------------------------------------------------------  
![引擎展示](https://images.gitee.com/uploads/images/2019/0911/100317_f9cf51d5_1658632.gif "MQ.gif")  
    ---------------------------------------------------------  
![引擎展示](https://images.gitee.com/uploads/images/2019/0911/100516_cf6fe0fa_1658632.gif "GIF1.gif")  
    ---------------------------------------------------------  
![点阵](https://images.gitee.com/uploads/images/2019/0911/100552_27b8c99d_1658632.gif "hsdz1.gif")  
    ---------------------------------------------------------  
![点阵 动态](https://images.gitee.com/uploads/images/2019/0911/100611_640dbdf0_1658632.gif "hsdz2.gif")  
    ---------------------------------------------------------  
![折线 动态](https://images.gitee.com/uploads/images/2019/0911/100639_b345356d_1658632.gif "zxdt.gif")  
    ---------------------------------------------------------  
![3D柱状 动态](https://images.gitee.com/uploads/images/2019/0911/100657_6b8b48b5_1658632.gif "dtzz.gif")  
    ---------------------------------------------------------  

![输入图片说明](https://gitee.com/uploads/images/2017/1204/204114_3c2c6022_1658632.png "1.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1204/204129_e1c89364_1658632.png "2.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1204/204137_0a5930ff_1658632.png "3.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1204/204143_10424c87_1658632.png "4.png")
![输入图片说明](https://gitee.com/uploads/images/2017/1204/204151_fe913a9b_1658632.png "5.png")

`Matplot3D for JAVA工具库采用外观（FACADE）设计模式提供方便的绘图API。`
`Matplot3DMgr 是工具库的外观类。其中常量属性成员如下`

    int	DATA_TYPE_DOTS
	            散点数据输入类型
    
    int	DATA_TYPE_FUNCTION3D
	    空间函数输入类型
    
    int	DATA_TYPE_CURVE2DS
	    二维折线输入类型
    
    int	DATA_TYPE_MATRIX 
	    数据阵列输入类型
    
    int	SHOW_TYPE_DOTS 
	    点状显示类型
    
    int	SHOW_TYPE_SURFACE
	    曲面显示类型
    
    int	SHOW_TYPE_PLAN_SHAPE
	    平面多边形显示类型
    
    int	SHOW_TYPE_PLANBARS
	    平面柱状图显示类型
    
`Matplot3DMgr的方法成员及说明如下：`

    void	show()
	    直接在独立的窗口中显示绘制图像
    
    boolean	updateView(long timeToWait) 
	    刷新绘制面板，并在timeToWait毫秒内阻止再刷新。如果刷新成功返回true,否则返回false。
    
    Jpanel	getPanel()
	    获取绘制面板JPanel对象。此对象与show()方法中现实的为同一对象，因此此方法不要和show()方法同时使用
    
    void	setDataInputType(int type)
	    设置输入数据模式。
        MatPlot3DMgr.DATA_TYPE_DOTS
        MatPlot3DMgr.DATA_TYPE_FUNCTION3D
        MatPlot3DMgr.DATA_TYPE_CURVE2DS
        MatPlot3DMgr.DATA_TYPE_MATRIX 
    
    void 	setShowType(int showType) 
	    设置输出显示模式。
        MatPlot3DMgr.SHOW_TYPE_DOTS 
        MatPlot3DMgr.SHOW_TYPE_SURFACE
        MatPlot3DMgr.SHOW_TYPE_PLAN_SHAPE
        MatPlot3DMgr.SHOW_TYPE_PLANBARS
    
    void 	addData2D(String key, Color color, List<Point2D.Double> pointsList)
	    输入模式为DATA_TYPE_CURVE2DS可用。
        加入在同一平面中的折线数据，并指定显示颜色
    
    void 	addData2D(String key, List<Point2D.Double> pointsList)
	    输入模式为DATA_TYPE_CURVE2DS可用。
        加入在同一平面中的折线数据
    
    void	addData(String key, List<Point3D> pointsList)
	    输入模式为DATA_TYPE_DOTS可用。
        加入一个系列的点位置数据。不同系列会显示不同的颜色和图形
    
    void 	addData(String key, double[][] matrix)
	    输入模式为DATA_TYPE_MATRIX 可用。
        加入一个系列的二维数量矩阵。一般用于显示柱状图
    
    void 	addData(Function function, Range rangeX, Range rangeY)
	    输入模式为DATA_TYPE_FUNCTION3D可用。
        设置一个函数并指定XY方向的定义域范围
    
    void 	addData(Function function, Range rangeX, Range rangeY, int stepCountX, int stepCountY)
	    输入模式为DATA_TYPE_FUNCTION3D可用。
        设置一个函数并指定XY方向的定义域范围,并指定XY方向分段数
    
    void	setScaleX(double scaleX)
	    设置X方向缩放比例
    
    void	setScaleY(double scaleY)
	    设置Y方向缩放比例
    
    void	setScaleZ(double scaleZ)
	    设置Z方向缩放比例
    
    double	getScaleX()
	    获取当前输入模式下X方向缩放比例
    
    double	getScaleY()
	    获取当前输入模式下Y方向缩放比例
    
        double	getScaleZ()
	    获取当前输入模式下Z方向缩放比例
    
    void	setFocusPerspectiveType(boolean flag)
	    设置是否为焦点透视三维显示模式
    
    void	setScatterPerspectiveType(boolean flag)
	    设置是否为散点透视三维显示模式
    
    void	setAntiAliasing(boolean isAntiAliasing)
	    设置是否抗锯齿显示（显示效果与计算机操作系统和机器性能有较大关系）
    
    void	setMouseDraggable(boolean isMouseDraggable)
	    设置是否支持鼠标交互控制。在设置值为true的情况下可以拖拽鼠标和滚动鼠标          滚轮，控制观察角度和缩放画面
    
    void 	setShowLegend(boolean isShowLegend)
	    设置是否支显示图例（如果有的话）
    
    void	setSeeta(double seeta)
	    设置视线俯仰角度
    
    void	setBeita(double beita)
	    设置视线方位角度
    
    double	getSeeta()
	    获取视线俯仰角度
    
    double	getBeita()
	    获取视线方位角度
    
    void	setFocusPoint(Point3D focusPoint)
	    设置观测中心点的三维坐标
    
    void	setTitle(String title) 
	    设置图标标题
    
    String 	getTitle()
	    获取图表标题
    
