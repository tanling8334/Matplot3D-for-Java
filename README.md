
# Matplot3D for Java


### 概述

 **Matplot3D for JAVA** 是一个基于JAVA  SE  1.8环境开发的三维图形图表组件。 **组件由纯JAVA SE 实现（Pure Java）** ，封装为一个jar包，jar文件大小不超过300KB。内含自主研发的三维几何造型、绘制算法，无需依赖OpenGL、DriectX和JAVA 3D等第三方库，其只依托JRE自带的类库即可（即只需安装了JAVA就可使用），可以非常方便的将Matplot3D for JAVA(V3.0)显示面板嵌入到自己JAVA GUI程序中。

本组件提供简单的外观API，可以方便生成三维效果的图形图表。可用于大数据可视化、科学数据分析可视化等领域。在使用GUI显示时支持鼠标等输入设备交互式操作，可方便的缩放和改变观察角度。支持动态编程，可实时生成三维模型动态改变动画。也可以根据输入的数据直接生成图片文件，这可用于动态Web的服务端，从页面传入的数据生成图像文件，返回给页面显示。

 **作者email:ta8334@126.com  ;  QQ :17746302** 

      

 **Matplot3d_4j_sydh_x64_V3.0.jar** 为应用所需要依赖的包。

 **Matplot3d_4j_sydh_x64_V3.0_demo.jar** 为演示DEMO的可执行的JAR文件，内含展示效果及部分示例代码， **使用时不需要引用这个包** 。如不清楚何运行可执行JAR的请自行百度一下（由于需要预载入的资源较多且展示多个画面，Demo启动会有点慢且会消耗较多内存，需要在64bit的JRE上运行）


### 效果展示


![地形数据动图](http://github.com/tanling8334/Matplot3D-for-Java/raw/master/pic/demo.gif "地形数据动图")  
    ---------------------------------------------------------  
![底层引擎展示动图（地球）](http://github.com/tanling8334/Matplot3D-for-Java/raw/master/pic/Earth.gif "底层引擎展示动图（地球）")  
    ---------------------------------------------------------  
![底层引擎展示动图（珠峰）](http://github.com/tanling8334/Matplot3D-for-Java/raw/master/pic/ZMLM.gif "底层引擎展示动图（珠峰）")  
    ---------------------------------------------------------  
![地形](http://github.com/tanling8334/Matplot3D-for-Java/raw/master/pic/地形.jpg "地形")  
    ---------------------------------------------------------  
![点云](http://github.com/tanling8334/Matplot3D-for-Java/raw/master/pic/点云.jpg "点云")  
    ---------------------------------------------------------  
![函数曲面](http://github.com/tanling8334/Matplot3D-for-Java/raw/master/pic/函数曲面.jpg "函数曲面")  
    ---------------------------------------------------------  
![混合数据](http://github.com/tanling8334/Matplot3D-for-Java/raw/master/pic/混合数据.jpg "混合数据")  
    ---------------------------------------------------------  
![马](http://github.com/tanling8334/Matplot3D-for-Java/raw/master/pic/马.jpg "马")  
    ---------------------------------------------------------  
![散点](http://github.com/tanling8334/Matplot3D-for-Java/raw/master/pic/散点.jpg "散点")  
    ---------------------------------------------------------  
![双函数曲面](http://github.com/tanling8334/Matplot3D-for-Java/raw/master/pic/双函数曲面.jpg "双函数曲面")  
    ---------------------------------------------------------  
![云图](http://github.com/tanling8334/Matplot3D-for-Java/raw/master/pic/云图.jpg "云图")  
    ---------------------------------------------------------  
![珠峰](http://github.com/tanling8334/Matplot3D-for-Java/raw/master/pic/珠峰.jpg "珠峰")  
    ---------------------------------------------------------  
![地](http://github.com/tanling8334/Matplot3D-for-Java/raw/master/pic/地球.jpg "地球")  
    ---------------------------------------------------------  
![折线](http://github.com/tanling8334/Matplot3D-for-Java/raw/master/pic/折线.jpg "折线")  
 ---------------------------------------------------------  
![柱状图](http://github.com/tanling8334/Matplot3D-for-Java/raw/master/pic/柱状图.jpg "柱状图")  



### API文档     



    1、类 Matplot3D4JMgr
类全名 tanling.matplot3d.app.facade.Matplot3D4JMgr
Matplot3D4JMgr类为主控制器，每一个Matplot3D4JMgr对象会对应一套显示资源，每一个绘制窗口或者显示面板都需要一个Matplot3D4JMgr对象，如果一个应用需要同时多个画面显示图形就必须创建多个Matplot3D4JMgr对象。可以理解为一个显示面板或者画面就对应一个Matplot3D4JMgr对象
在不需要GUI显示的时候，Matplot3D4JMgr对象可在服务端生成保存图像文件，提供给动态Web页面使用，即可以让浏览器传入参数生成三维图片后发送回浏览器显示。
Matplot3D4JMgr必须结合Processor对象使用。Processor及其子类为数据处理器类（详见Processor类和其子类的说明和API部分文档）一个Matplot3D4JMgr对象必须至少持有一个数据处理器类（Processor类的具体实现子类）的对象。其中必须有一个Processor对象为该Matplot3D4JMgr对象的默认数据处理器。Matplot3D4JMgr持有的所有Processor的数据都可以在同一画面生成图形图像，但是只有默认数据处理器的图例会显示。
1.1公共字段

public  final  static int COORDINATE_RANGE_AUTO_EXTEND
动态编程中，坐标系的变化类型。当设置为此类型时，坐标系会随数据自动扩展但不会自动收缩。


public  staticfinal int	COORDINATE_RANGE_AUTO_FIT
动态编程中，坐标系的变化类型。当设置为此类型时，坐标系会随数据自动扩展和自动收缩。

R
public static final int COORDINATE_SYS_ALWAYS_FURTHER
坐标系显示状态类型，当设置为此类型时，无论观察角度如何，坐标系始终在数据的“后方”。


public  staticfinal int	COORDINATE_SYS_STABLE
坐标系显示状态类型，当设置为此类型时，坐标系在空间中的朝向是固定不变的。

1.2构造方法

public Matplot3D4JMgr(Processor  processor)
创建具有指定默认处理器processor的Matplot3D4JMgr对象。

1.3方法

public  void addProcessor(Processor processor)
向Matplot3D4JMgr对象中增加一个Processor处理器，Matplot3D4JMgr中可以指定不止一个处理器。


public  void clearBuffer()
清除本Matplot3D4JMgr对象的显示相关缓存，以便可以释放部分对象引用等待垃圾回收。当程序中有多个Matplot3D4JMgr对象时，如果某些Matplot3D4JMgr对应的界面没有显示出来（例如被最小化），则可以清除缓存以便gc释放内存。


public  void fitScreem()
在本Matplot3D4JMgr对象对应的界面正在显示时，自动适配图像内容的大小比例。在对应的界面不显示时（例如被最小化），此方法无效。


public  double getBeita()
获取观察的方位角弧度（0到2π），以x轴正向为0。


public  Processor getDefProcessor()
获取本Matplot3D4JMgr对象的默认Processor。


public  JPanel getPanel()
获取显示内容的JPanel对象。


public  Processor[] getProcessors()
获取本Matplot3D4JMgr对象已经添加的所有Processor对象的数组。


public  double getScaleX()
获取X方向缩放比例的数值。


public  double getScaleY()
获取Y方向缩放比例的数值。


public  double getScaleZ()
获取Z方向缩放比例的数值。


public  double getSeeta()
获取观察的俯仰角弧度（-π/2到π/2）。


public  void removeProcessor(Processor processor)
删除一个已经添加的processor对象。


public  void saveImage(File file, int width, int height)
保存生成的图像到指定文件。可用于动态WEB页面，根据浏览器传入的参数生成图片返回浏览器端显示。参数 file为指定文件，width是图片高，height是图片宽。


public  void setAxisNameTextColor(Color color)
设置X轴名文字颜色。


public  void setAxisNameTextFont(Font font)
设置X轴名文字字体。


public  void setBeita(double beita)
设置观察的方位角弧度（设置值为0到2π），以x轴正向为0，从X轴正向向Y轴正向旋转。


public  void setCoordianteSysShowType(int type)
设置坐标系的显示位置方式。参数type值可取值COORDINATE_SYS_ALWAYS_FURTHER或者COORDINATE_SYS_STABLE


public  void setCoordianteSysTransformationType(int type)
动态编程中，设置坐标系的变化方式。参数type值可取值COORDINATE_RANGE_AUTO_EXTEND或者COORDINATE_RANGE_AUTO_FIT


public void setDefaultProcessor(Processor defaultProcessor)
设置defaultProcessor为默认Processor，如果defaultProcessor原先未添加在本defaultProcessor对象中，该方法会同时将其加入。


public void setFocusPerspectiveType(boolean flag)
设置焦点透视成像，设置true时为焦点透视，为false为散点透视


public void setGlobalBrightness(double brightness)
设置全局亮度，brightness要求>=0, brightness为1.0时为默认亮度。


public void setMouseDraggable(boolean flag)
设置是否支持鼠标旋转缩放交互操作


public void setRulerLabelsX(String[] labels, double[] positions)
设置用户自定义的坐标系X轴标尺刻度字符串和对应的刻度位置。


public void setRulerLabelsY(String[] labels, double[] positions)
设置用户自定义的坐标系Y轴标尺刻度字符串和对应的刻度位置。


public void setRulerLabelsZ(String[] labels, double[] positions)
设置用户自定义的坐标系Z轴标尺刻度字符串和对应的刻度位置。


public void setRulerTextColor(Colorcolor)
设置坐标系标尺刻度字符串颜色。


public void setRulerTextFont(Font  font)
设置坐标系标尺刻度字符串字体。


public void setRulerXVisable(booleanflag)
设置坐标系X轴标尺是否显示。


public void setRulerYVisable(booleanflag)
设置坐标系Y轴标尺是否显示。


public void setRulerZVisable(booleanflag)
设置坐标系Z轴标尺是否显示。


public void setScaleX(doublescale)
设置X方向的显示缩放比例，scale为1.0时为100%。此方法不会改变空间坐标数据，仅仅是将显示拉伸或压缩


public void setScaleY(doublescale)
设置Y方向的显示缩放比例，scale为1.0时为100%。此方法不会改变空间坐标数据，仅仅是将显示拉伸或压缩


public void setScaleZ(doublescale)
设置Z方向的显示缩放比例，scale为1.0时为100%。此方法不会改变空间坐标数据，仅仅是将显示拉伸或压缩


public void setScatterPerspectiveType(boolean flag)
设置散点透视成像，设置false时为焦点透视，为true为散点透视


public void setSeeta(doubleseeta)
设置观察的俯仰角弧度（-π/2到π/2）。


public void setShowLegend(boolean flag)
设置是否显示图例，如果有多个Processor处理器则只去默认Processer的图例


public void setShowReferencePlanes(boolean flag)
设置是否显示参考坐标系。


  public void setTitle(String  title)
设置标题


public void setXAccuracy(short accuracy)
设置X轴的标尺的数字精度（即小数位数）


public void setXAfterText(String Text)
设置X轴的标尺的刻度字符串的后缀（例如物理量单位）


public void setXName(String name)
设置X轴的标尺的名字


public void setXNameVisable(boolean flag)
设置是否显示X轴的标尺


public void setXPreText(String text)
设置X轴的标尺的刻度字符串的前缀。


public void setXTranslater(IDecimalTranslatertranslater)
设置X轴的标尺刻度字符串的自定义转换器（详见接口IDecimalTranslater 的说明）


public void setYAccuracy(short accuracy)
设置Y轴的标尺的数字精度（即小数位数）


public void setYAfterText(String Text)
设置Y轴的标尺的刻度字符串的后缀（例如物理量单位）


public void setYName(String name)
设置Y轴的标尺的名字


public void setYNameVisable(boolean flag)
设置是否显示Y轴的标尺


public void setYPreText(String text)
设置Y轴的标尺的刻度字符串的前缀。


public void setYTranslater(IDecimalTranslatertranslater)
设置Y轴的标尺刻度字符串的自定义转换器（详见接口IDecimalTranslater 的说明）。


public void setZAccuracy(short accuracy)
设置Z轴的标尺的数字精度（即小数位数）


public void setZAfterText(String Text)
设置Z轴的标尺的刻度字符串的后缀（例如物理量单位）


public void setZName(String name)
设置Z轴的标尺的名字


public void setZNameVisable(boolean flag)
设置是否显示Z轴的标尺


public void setZPreText(String text)
设置Z轴的标尺的刻度字符串的前缀。


public void setZTranslater(IDecimalTranslatertranslater)
设置Z轴的标尺刻度字符串的自定义转换器（详见接口IDecimalTranslater 的说明）。


public void show()
直接在独立的窗口中显示绘制图像。


public boolean updateView(long timeToWait)
刷新绘制面板，并在timeToWait毫秒内阻止再刷新。如果刷新成功返回true,否则返回false。

    2、抽象类 Processor
类全名 tanling.matplot3d.app.facade.Processor

2.1方法

public abstract void clear();
此为抽象方法。清除本Processor对象的所有数据下次，刷新后与本Processor对象相关的数据将不再画面上显示。


public void initRanges(Range rangeX, Range rangeY, Range rangeZ)
初始化坐标系的xyz三个方向的空间范围。


public abstract void setShowType(int  type)
此为抽象方法,具体的Processor类中对相同的数据可能有不同的显示方式。如果有则通过此方法设置显示方式。（例如数据阵列可以显示为“点阵”或者“曲面”等不同的形式）


public void setFillArea(boolean  flag)
如果显示内容可能需要填充（例如曲面），此方法设置是否填充。


public void setHolder(Matplot3D4JMgrmgr)
设置Matplot3D4JMgr对象持有者，一般不需要手动调用，每一个具体的Processor对象都与一个Matplot3D4JMgr 相关。

    3、类 FunctionProcessor
    类全名 tanling.matplot3d.app.facade.FunctionProcessor
FunctionProcessor 类继承自Processor类。函数处理器类，根据函数表达生成三维图形。
3.1公共字段

    public  static int SHOW_TYPE_SURFACE
以曲面方式显示。用于Processor类中的setShowType(int  type)方法。


    public  static int SHOW_TYPE_DOTS
以点阵方式显示。用于Processor类中的setShowType(int  type)方法。

3.2方法

public void addData(Function f, String name, Range rangeX, Range rangeY)
加入一项函数数据，并指定定义域。参数说明如下：
1、f:函数对象（详见接口Function文档）；
2、name：名字；
3、rangeX：自定义域的X范围；
4、rangeY：自定义域的Y范围。


public void addData(Function f, String name, Range rangeX, Range rangeY, int stepX, int stepY)
加入一项函数数据，并指定定义域和X，Y方向上的分段数。参数说明如下：
1、f:函数对象（详见接口Function文档）；
2、name：名字；
3、rangeX：自定义域的X范围；
4、rangeY：自定义域的Y范围；
5、stepX：x方向上的分段数；
6、stepY：y方向上的分段数；


public void addData(Function f, String name, Color color, Range rangeX, Range rangeY, int stepX, int stepY, float alpha)
加入一项函数数据，并指定定义域、X，Y方向上的分段数,颜色和透明度。参数说明如下：
1、f:函数对象（详见接口Function文档）；
2、name：名字；
3、color：着色颜色 
4、rangeX：自定义域的X范围；
5、rangeY：自定义域的Y范围；
6、stepX：x方向上的分段数；
7、stepY：y方向上的分段数；
8、alpha：不透明度（0为完全透明，1.0为完全不透明）。


public void addData(Function f, String name, Range rangeX, Range rangeY, int stepX, int stepY, ColorStyle cs, float alpha)
加入一项函数数据，并指定定义域、X，Y方向上的分段数，颜色配色风格对象和透明度。参数说明如下：
1、f:函数对象（详见接口Function文档）；
2、name：名字；
3、rangeX：自定义域的X范围；
4、rangeY：自定义域的Y范围；
5、stepX：x方向上的分段数；
6、stepY：y方向上的分段数；
7、cs: 自定义颜色配色风格对象（详见接口ColorStyle文档）
8、alpha：不透明度（0为完全透明，1.0为完全不透明）。


public static Double[][] getDMatrixByFunction(Function f, Range rangeX, Range rangeY, int stepX, int stepY)
静态工具方法：根据函数对象，定义域范围和采样分段数生成二维数组。参数说明如下：
1、f:函数对象（详见接口Function文档）；
2、rangeX：自定义域的X范围；
3、rangeY：自定义域的Y范围；
4、stepX：x方向上的采样分段数；
5、stepY：y方向上的采样分段数。


public void setLegendAccuracy(short  accuracy)
设置图例数字显示精度（小数位数）。


public void setLegendAfterText(String text)
设置图例数字显示字符串的后缀（例如物理量单位）。


public void setLegendPreText(String text)
设置图例数字显示字符串的前缀。


public void setLegendTranslater(IDecimalTranslatertranslater)
设置图例字符串的自定义转换器（详见接口IDecimalTranslater 的说明）。


public void setShowGrid(boolean  flag)
设置是否显示曲面网格线。


public void setSmooth(boolean  flag)
设置是否进行曲面平滑显示。

    4、接口 Function
    类全名 tanling.matplot3d.app.facade.Function
接口Function 表示一个二维函数，根据x,y自变量值得到函数z值
4.1方法

public abstract Double f(double x, double y)
根据x,y自变量值得到函数z值

    5、类 DataGridProcessor
    类全名 tanling.matplot3d.app.facade.DataGridProcessor
DataGridProcessor类继承自FunctionProcessor类。DataGridProcessor是数据网格处理器。数据网格是指一个在x，y方向都均匀排列的点阵列。使用一个Double[][]表示数据，数组中的值为z（高度）值，值可以为null。x,y方向由于均匀分布，。在指定了各自的取值范围后即可换算为空间坐标的x,y坐标。需要注意的是Double[][]中存放的为数据，和显示的分段数不一定相等。

5.1方法

public void addData(Double[][] data, String name, Color color, Range rangeX, Range rangeY, int  stepX, int stepY, float alpha)
加入一组数据阵列数据，并指定x,y范围，显示分段,颜色和不透明度。参数说明如下：
1、data:数据阵列二维数组，第一个下标代表X方向,第二个下标代表Y方向；
2、name：名字；
3、color：颜色；
4、rangeX：数据在X方向的分布范围；
5、rangeY：数据在Y方向的分布范围；
6、stepX ：X方向的显示分段。（PS：显示分段数和data的两个维度的数组长度可以不一致）；
7、stepY：Y方向的显示分段。（PS：显示分段数和data的两个维度的数组长度可以不一致）；
8、alpha：不透明度（0为完全透明，1.0为完全不透明）。


public void addData(Double[][] data, String name, Range rangeX, Range rangeY, int stepX, int stepY, ColorStyle cs, float alpha)
加入一组数据阵列数据，并指定x,y范围，显示分段,颜色配色风格和不透明度。参数说明如下：
1、data:数据阵列二维数组，第一个下标代表X方向,第二个下标代表Y方向；
2、name：名字；
3、rangeX：数据在X方向的分布范围；
4、rangeY：数据在Y方向的分布范围；
5、stepX：X方向的显示分段。（注意：显示分段数和data的两个维度的数组长度可以不一致）
6、stepY：Y方向的显示分段。（注意：显示分段数和data的两个维度的数组长度可以不一致）
7、cs：自定义颜色配色风格对象（详见接口ColorStyle文档）；
8、alpha：不透明度（0为完全透明，1.0为完全不透明）。


public void setClose3DObject(boolean flag)
设置是否封闭三维对象，如果为false则只显示数据曲面，如果为true则将曲面、z=0的矩形平面和四周的垂直面将三维图形围蔽。

    6、类 ContourDataGridProcessor
    类全名 tanling.matplot3d.app.facade.ContourDataGridProcessor
ContourDataGridProcessor类继承自DataGridProcessor类。ContourDataGridProcessor是“数据网格云图处理器”。“云图”包含xyz三个空间量以外还会显示第4个独立的标量（例如温度、压强、流速率等等）的分布，第4个量强弱由颜色序列来表示。

6.1方法

public void addData(Double[][] data, Double[][] values, Color color, TopBottomColorStyle cs, String name, Range rangeX, Range rangeY, int stepX, int stepY, float alpha)
加入一组数据阵列数据，并指定x,y范围，显示分段,颜色风格和不透明度。参数说明如下：
1、data：z数据阵列二维数组，第一个下标代表X方向,第二个下标代表Y方向；
2、values：xyz之外的第4个独立量的二维数组（其中的值可以为null，数组的形状可以与data不一致）
3、color：基色,当某个位置第4变量为null时（注意不是为0时）会显示基色；
4、cs：TopBottomColorStyle颜色配色风格（根据xyz之外的第4个独立量值获取某个位置的显示颜色），详见TopBottomColorStyle文档介绍。
5、name：名字；
6、rangeX：数据在X方向的分布范围；
7、rangeY：数据在Y方向的分布范围；
8、stepX：X方向的显示分段。
9、stepY：Y方向的显示分段。
10、alpha：不透明度（0为完全透明，1.0为完全不透明）。


public void addData(Double[][] data, Double[][] values, Color color, String name, Range rangeX, Range rangeY, int stepX, int stepY, float alpha)
加入一组数据阵列数据，基本与前方法相同，只是采用默认的配色颜色风格。参数说明如下：
1、data：z数据阵列二维数组，第一个下标代表X方向,第二个下标代表Y方向；
2、values：xyz之外的第4个独立量的二维数组（其中的值可以为null，数组的形状可以与data不一致）
3、color：基色,当某个位置xyz之外的第4个独立量为null时（注意不是为0时）会显示基色；
4、name：名字；
5、rangeX：数据在X方向的分布范围；
6、rangeY：数据在Y方向的分布范围；
7、stepX：X方向的显示分段。
8、stepY：Y方向的显示分段。
9、alpha：不透明度（0为完全透明，1.0为完全不透明）。


public void addData(Double[][] data, Double[][] values, Color color, String name, ValueRangeColorStyle  cs, Range rangeX, Range rangeY, int stepX, int stepY, float alpha)
加入一组数据阵列数据，基本与前方法相同，只是指定输入ValueRangeColorStyle类型的颜色配色风格，详见ValueRangeColorStyle文档介绍。参数说明如下：
1、data：z数据阵列二维数组，第一个下标代表X方向,第二个下标代表Y方向；
2、values：xyz之外的第4个独立量的二维数组（其中的值可以为null，数组的形状可以与data不一致）
3、color：基色,当某个位置xyz之外的第4个独立量为null时（注意不是为0时）会显示基色；
4、name：名字；
5、cs：ValueRangeColorStyle 颜色配色风格（根据xyz之外的第4个独立量值获取某个位置的显示颜色），详见ValueRangeColorStyle 文档介绍。
6、rangeX：数据在X方向的分布范围；
7、rangeY：数据在Y方向的分布范围；
8、stepX：X方向的显示分段。
9、stepY：Y方向的显示分段。
10、alpha：不透明度（0为完全透明，1.0为完全不透明）。

    7、类 LineChartProcessor
类全名 tanling.matplot3d.app.facade.LineChartProcessor 
LineChartProcessor 类继承自Processor类。LineChartProcessor 是折线图数据处理器。

7.1方法

public void addData(String  name, Color color, List<Point2D.Double> pointList)
加入一组数据折线数据，并指定名称和颜色，参数说明如下：
1、name：这组数据的名字，名字会显示在图例上；
2、color：这组数据折线显示的颜色；
3、pointList：数据折线的二维点序列，由于同一组数据会在同一个平面，因此使用二维点表示，二维点的x对应空间中的x，二维点的y对应空间中的z；


public void addData(String  name, List<Point2D.Double>pointList)
加入一组数据折线数据,指定名称同时自动分配颜色，参数说明如下：
1、name：这组数据的名字，名字会显示在图例上；
2、pointList：数据折线的二维点序列，由于同一组数据会在同一个平面，因此使用二维点表示，二维点的x对应空间中的x，二维点的y对应空间中的z；

    8、类 DotsDataProcessor
类全名 tanling.matplot3d.app.facade.DotsDataProcessor
DotsDataProcessor类继承自Processor类。DotsDataProcessor是无序散点数据处图形理器。可用于展示点云数据

8.1方法

public void addData(String  name, Collection<Point3D> point3ds)
加入一组无序散点数据，指定名称同时自动分配颜色，参数说明如下：
1、name：这组数据的名字，名字会显示在图例上；
2、point3ds：本组包含的三维点数据；


public voidaddData(String  name, Color  color, Collection<Point3D> point3ds)
加入一组无序散点数据,指定名称同时自动分配颜色，参数说明如下：
1、name：这组数据的名字，名字会显示在图例上；
2、color：本组点显示的颜色；
3、pointList：数据折线的二维点序列，由于同一组数据会在同一个平面，因此使用二维点表示，二维点的x对应空间中的x，二维点的y对应空间中的z；


public void setDrawPixel(booleanflag)
设置本处理器对象含有的数据是否用一个像素绘制一个点数据。设置flag为true则一个像素绘制一个点数据,如果设置flag为false则用一个系统自定的小几何图形绘制点。

    9、类 HistogramProcessor
    类全名 tanling.matplot3d.app.facade.HistogramProcessor
HistogramProcessor类继承自Processor类。HistogramProcessor是柱状图处理器，也添加多组数据生成多排分组的柱状图

9.1方法

public void addData(String  name, double[][]  data)
加入一组柱状图数据，指定该组数据的名称，参数说明如下：
1、name：这组数据的名字，名字会显示在图例上；
2、data：一个二维数组，数组中的数字表示方柱高度；数组第一个下标代表该组排列行号，第二个下标代表该组排列列号。

    10、接口 ColorStyle
   类全名 tanling.matplot3d.d3d.color_style.ColorStyle
接口ColorStyle表示一个颜色配色风格，它可定义一个一维的线性颜色空间（可以理解为一个颜色序列），颜色空间对应一段数值的范围（用颜色代表数值大小）。并通过空间位置及自定义的参数或者属性给连续的曲面着色，具体的实现类可定义不同的着色逻辑。 主要用于FunctionProcessor及其子类DataGridProcessor，ContourDataGridProcessor的图形颜色配色。本组件已实现了两个具体的ColorStyle类，分别为TopBottomColorStyle和ValueRangeColorStyle，详见他们的文档说明。（此接口为模板方法设计模式，其所有方法一般不用开发者显示调用，皆由系统完成调用。PS：自实现ColorStyle具体类难度较大）

10.1方法

public abstract void setPrar(Object paramObject)
设置使用者自定义需要的用于计算颜色的参数，使用者已定义的颜色分布可能需要外部对象作为参数，使用此方法可传入任意类的对象作为参数（包括数组和容器对象）。一般会将参数对象设置为具体实现类的私有成员。


public abstract Color getColor(Point3D  p3d)
根据输入的三维点计算输出的颜色，三维点p3d中包含坐标信息，具体实现该方法时根据点的三维坐标和由setPrar方法输入的参数对象计算出对应的颜色。


public Color[] getColors(Range range ,int colorsCount)
获取一个数值范围range 对应要显示的颜色序列（注意这里是需要的连续的颜色序列，而不仅仅是关键色颜色序列），用于获取在图例色条。参数说明如下：
1、range ：一个需要显示的数值范围；
2、colorsCount：对应的颜色渐变序列的颜色数（不是关键色数，而是全部渐变色数）；


public Color[] getKeyColors()
获取本ColorStyle对象的完整颜色序列的关键色序列，关键色为颜色序列中独立的数个颜色，关键色之间的颜色会过渡渐变。头尾关键色会对应颜色序列的顶点，中间的关键色则会平均切分颜色序列。（关键色数量为大于等于2的整数。例如关键色共4个，依次为红，橙，绿，蓝，假设整个颜色序列的总颜色数为100个，则红色在第1位，蓝色在第100位，橙色在约第33-34位处，绿色约在第66-67位处，其余位置的颜色将根据前后最近的两个关键色过渡生成。）


public Range getValueRange()
获取本ColorStyle对象对应的整个数值范围。

    11、类 TopBottomColorStyle
    类全名 tanling.matplot3d.d3d.color_style. TopBottomColorStyle
TopBottomColorStyle类是接口ColorStyle的一个具体实现类，其定义一个监控曲面高度范围的ColorStyle。无论高度范围的具体数值如何，最高值和最低值始终对应颜色空间的最高色和最低色，即无论数值范围跨度大小，它都会对应完整的颜色空间。

11.1构造方法

public TopBottomColorStyle()
构造一个简单的默认红蓝高低色颜色空间的TopBottomColorStyle。


public TopBottomColorStyle(Color... keyColors)
构造一个自定义具有高低色颜色空间的TopBottomColorStyle，自定义颜色空间由输入的关键色数组keyColors确定。

    12、类 ValueRangeColorStyle
    类全名 tanling.matplot3d.d3d.color_style. ValueRangeColorStyle
ValueRangeColorStyle类是接口ColorStyle的一个具体实现类，其定义一个确定数值对应确定颜色的ColorStyle。颜色序列的范围对应确定的连续数值范围区间（例如红蓝颜色空间对应[0,100]的数值区间），数值区间内的子区间会映射到颜色空间对应的子区间。如果某个数值高于预定义的数值区间最大值，则这个数值会对应最高色。反之某个数值低于预定义的数值区间最小值则对应最低色。

12.1构造方法

public ValueRangeColorStyle (Range range)
构造一个简单的默认红蓝高低色颜色空间,数值空间为range的ValueRangeColorStyle。（类Range详见其说明文档）
ValueRangeColorStyle
public ValueRangeColorStyle (Range range , Color... keyColors)
构造一个自定义具有高低色颜色空间,数值空间为range的ValueRangeColorStyle。自定义颜色空间由输入的关键色数组keyColors确定。（类Range详见其说明文档）

    13、类 Point3D
    类全名 tanling.matplot3d.common.Point3D
Point3D表示一个三维空间的点。

13.1构造方法

public  Point3D(double  x , double  y , double  z)
用坐标值x,y,z构造一个点对象。参数说明如下：
1、x ：坐标x值；
2、y ：坐标y值；
3、z ：坐标z值。

13.2方法

public  double  x()
获取本Point3D对象的x坐标。


public  double  y()
获取本Point3D对象的y坐标。


public  double  z()
获取本Point3D对象的z坐标。


public  double  x( double  newX)
重设置本Point3D对象的x坐标值为newX。


public  double  y( double  newY)
重设置本Point3D对象的y坐标值为newY。


public  double  z( double  newZ)
重设置本Point3D对象的z坐标值为newZ。

    14、类 Range
    类全名 tanling.matplot3d.common.Range
Range表示一个连续的数值区间范围，例如[1 , 100] , [-20.1 , 3300.3]等等。

14.1构造方法

public  Range(double  d1, double  d2)
创建以d1,d2为两端的数值区间，d1,d2大小先后顺序没有要求（即new Range(1.0,2.0)和new Range(2.0,1.0)是一样的）。参数说明如下：
1、d1 ：数值范围一端的值；
2、d2 ：数值范围另一端的值。

14.2方法

public  boolean  contains(double  value)
判断一个数值是不是在本Range对象所表示的区间，如果数值刚好落在两个端点也返回true。


public  double getBegin()
返回本Range对象代表的区间最小值。


public  double  getEnd()
返回本Range对象代表的区间最大值。


public  double  getRangeCenter()
返回本Range对象代表的区间中点值。


public  double  getRangeValue()
返回本Range对象代表的区间区间范围（最大值-最小值）。


public  static  Range  merge(Range range1, Range range2)
静态工具方法，将两个Range对象合并返回一个新的Range对象，执行该方法后原现两个Range对象不变。


public  void  reset(double  d1, double  d2)
重设置本Range对象为以d1,d2为两端的数值区间，d1,d2大小先后顺序没有要求（即new Range(1.0,2.0)和new Range(2.0,1.0)是一样的）。参数说明如下：
1、d1 ：数值范围一端的值；
2、d2 ：数值范围另一端的值。
