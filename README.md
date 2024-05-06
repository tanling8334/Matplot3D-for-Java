# Matplot3D for Java


### 概述

  在数据科学和工程领域，数据可视化是理解和交流复杂信息的关键工具。如果您是一位Java开发者，寻找一个强大的、本地化的三维图形绘图库，那么Matplot3D for JAVA（V5.0）值得你关注。该组件旨在为Java开发者提供类似于Python中Matplotlib的三维绘图功能，让Java也能轻松绘制出令人印象深刻的3D图形图表。

  **Matplot3D for JAVA（V5.0）** 是一个基于JAVA SE环境开发的三维图形图表组件。 组件由纯JAVA SE 实现（Pure Java） ，封装为一个jar包，jar文件大小只有300多KB。内含自主研发的软件三维几何造型和绘制算法，无需依赖OpenGL、DriectX、JAVA 3D或JAVAFX等等第三方库，其只依托JRE自带的默认类库即可（即只需安装了JAVA就可使用）。

  **Matplot3D for JAVA（V5.0）** 提供简洁明了的API设计，这使得即使是没有太多数据可视化工经验的开发者也可以快速上手构建出交互式的可视化应用。可用于大数据可视化、科学数学数据分析可视化等领域。它利用Java的自带的GUI框架构建界面同，确保了良好的跨平台兼容性同时能方便的集成到自己JAVA GUI程序中。也可以在服务端直接生成图片对象或文件，用于动态Web页面显示。

---

### 应用场景
  

- 教学和研究：用于展示数学模型、物理现象和数据等。
- 数据科学：在数据分析过程中可视化三维数据，帮助发现潜在模式。
- 其他需要数据可视化的Java应用和系统


---

### 包文件说明

 **Matplot3d_4j_sydh_x64_V5.0.jar** 为应用所需要依赖的包，仅将此包文件导入项目即可使用。

 **Matplot3d_4j_sydh_x64_V5.0_demo.jar** 为演示DEMO的可执行的JAR文件，内含展示效果及部分示例代码， **使用时不需要引用这个包** 。如不清楚何运行可执行JAR的请自行百度一下（需要在64bit的JRE上运行）  

---
### 作者联系方式
 **email:ta8334@126.com  ;  QQ :17746302** 

---

### 效果展示

**C60分子结构**

![C60分子结构](pic/C60.gif "C60分子结构")     
<br/> 
<br/> 
￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣

**电荷矢量场**

![电荷矢量场](pic/GIF8.gif "地形数据动图")  
<br/> 
<br/> 
￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣

**地形数据**

![地形数据动图](pic/demo.gif "地形数据动图")  
<br/> 
<br/> 
￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣

**网格曲面** 

![网格曲面](pic/网格曲面.jpg "网格曲面")  
<br/> 
<br/> 
￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣

**矢量场流线** 

![矢量场流线](pic/线圈电流磁场.gif "矢量场流线") 

'''
public class SimpleVectorFieldDemo {
	public static void main(String[] args) {

		VectorFieldProcessor processer = new VectorFieldProcessor();

		Matplot3D4JMgr matPlot3DMgr = new Matplot3D4JMgr(processer);

		Vector3D v1 = new Vector3D(1, 0, 0);
		Vector3D v2 = new Vector3D(-0.1, 0, 0);
		Vector3D vNull = new Vector3D(0, 0, 0);

		class MyMapper1 implements Point3dVector3dMapper {
			public Vector3D f(Point3D p) {
				if (p.y() > 0) {
					return v1;
				} else {
					return vNull;
				}
			}

			public void setAdditionalPrar(Object additionalprar) {}
		}

		class MyMapper2 implements Point3dVector3dMapper {
			public Vector3D f(Point3D p) {
				if (p.y() < 0) {
					return v2;
				} else {
					return vNull;
				}
			}

			public void setAdditionalPrar(Object additionalprar) {}
		}

		processer.addData(new MyMapper1(), "1", Color.RED, new Range(-9, 9), new Range(-9, 9), new Range(-9, 9));

		processer.addData(new MyMapper2(), "2", Color.BLUE, new Range(-9, 9), new Range(-9, 9), new Range(-9, 9));

		List<Point3D> seeds = new ArrayList<Point3D>();

		for (double z = -9; z <= 9; z += 1.2) {
			for (double y = -9; y <= 9; y += 1.2) {
				seeds.add(new Point3D(0, y, z));
			}
		}

		processer.setPropertyToAll("seeds", seeds);
		processer.setPropertyToAll("alphaNoise", 0.0);

		matPlot3DMgr.setTitle("矢量场流线");
		matPlot3DMgr.setAppearanceTheme(Matplot3D4JMgr.APPEARANCE_THEME_DARK);

		matPlot3DMgr.setCoordianteSysShowType(Matplot3D4JMgr.COORDINATE_SYS_ALWAYS_FURTHER);

		matPlot3DMgr.showMotion(-1, 15, 0);
	}
}
'''

<br/> 
<br/> 
￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣

**数据阵列曲面** 

![数据阵列曲面](pic/数据阵列曲面.jpg "数据阵列曲面")  
<br/> 
<br/> 
￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣

**通用网格** 

![通用网格](pic/通用网格.jpg "通用网格")  
<br/> 
<br/> 
￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣

**曲面云图** 

![曲面云图](pic/曲面云图.jpg "曲面云图")  
<br/> 
<br/> 
￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣

**柱状图** 

![柱状图](pic/柱状图.jpg "柱状图")  
<br/> 
<br/> 
￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣

**瀑布图** 

![瀑布图](pic/瀑布图.jpg "瀑布图")  
 <br/> 
<br/> 
￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣

**点云散点** 

![点云散点](pic/点云散点.jpg "点云散点")  
 <br/> 
<br/> 
￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣

**简单几何体** 

![简单几何体](pic/简单几何体.jpg "简单几何体")  
 <br/> 
<br/> 
￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣￣

**折线曲线** 

![折线曲线](pic/折线曲线.jpg "折线曲线")  
 <br/> 
<br/> 






    



