# DogKnight
## 该说明仅针对此项目 此项目为端游3D RPG URP渲染管线
### Unity版本 2022.1.12  

### 关于3D默认渲染管线升级到URP管线
首先在Package Manager中安装Universal RP 之后在project窗口中Create-->Rendering-->URP Asset 然后在Edit窗口中Project Settings-->Graphics中添加新建的URP Asset 在Project Settings-->Quality也添加URP Asset 最后在Window窗口中Rendering-->Render Pipeline Converter窗口中下拉选择Build-in to URP后勾选下方全部选择框后initialize Converters后Convert Assets即可渲染URP素材

### 关于天空盒
在Window窗口中Rendering-->Lighting窗口下Environment-->Skybox Material更换需要的天空盒材质即可

### 关于阴影
URP Asset下更改Shadows的Max Distance可以调整渲染阴影的距离 更改Shadows的Cascade Count可以进行分级渲染 达到近实远虚的效果 更改Shadows的Split可以选择层级渲染距离 勾选Shadows的Soft Shadows可以使阴影模糊 更改Shadows的Normal Bias可以让影子有虚实变化 更改Lighting下的Shadow Resolution可以更改阴影分辨率 更改Quality的Anti Aliasing(MSAA)可以更改抗锯齿

### 关于光照
更改GameScene Settings中的灯光，若没有则在Window窗口中Rendering-->Lighting-->Scene下New Lighting Settings即可 Lightings Mode一般选择Baked indirect间接烘焙 Lightmapper一般选择Progressive GPU（Preview）减少CPU开销 设置好后点击右下角的Generate Lighting即可 在Environment下更改Environment Lighting-->Source可以选择环境光

### 关于场景道具
按住V拖拽道具可以使用顶点吸附 方便场景中道具环境布置 调整好Scene窗口后选中Main Camera后Ctrl+Shift+F可以将摄像机固定到Scene当前角度视角

### 关于Polybrush插件绘制地图物体
在Window-->Package Manager下找到Polybrush下载后需要Import对应的Samples 后在Tools-->Polybrush-->Polybrush Window可以打开Polybrush插件 第一栏可以调整地面的高矮 点击后在三角面上点击左键可以拉高 按住Ctrl+左键可以拉低 其中Outer Radius外角可以调整外圈 Inner Radius内角可以调整内圈 Strength可以调整拉扯力度 Direcetion可以调整拉扯方向 Brush Mirroring可以复制笔刷沿XYZ轴对称刷 第二栏可以柔化场景 将场景中的顶点进行柔化处理 第三栏可以在物体上刷颜色 将Import的Shader Lit Vertex Color URP做成材质球挂在地面上后即可使用刷上颜色 Flood可以直接填充全部 第四栏可以刷上预制体 将预制体放入Current Palette中选择后在Brush Loadout中可以看到选择的预制体 下方的滚条可以设置出现概率 可以多选预制体 放置时随机出现选择的预制体 刷预制体时尽量勾选 Hit surface is parent将预制体生成在当前物体子集下 按住Ctrl点按可以消除场景中刷上的预制体 但是要保证Brush Loadout中有当前预制体 第五栏可以在场景中刷Texture 方法同第四栏

### 关于ProBuilder插件绘制地面
在Window-->Package Manager下找到ProBuilder下载后需要Import对应的Samples 后在Tools-->ProBuilde-->ProBuilde Window可以打开ProBuilde插件 选择右上方Use Icon Mode 使用图形模式 选择New Shape后按住左键选择范围可以更改不同的模型进行范围适配 参数可以从生成物体挂载的脚本Pro Builder Shape中更改Size可以更改物体大小 Plane Settings-->Height Cuts和Width Cuts可以更改顶点数 ProBuilder栏中选择Triangulate Object可以将方形面切割成三角面 创建出来的Plane可以用材质球直接附上材质即可

### 关于ProGrids插件
安装ProGrids插件前先需要从Edit-->Project Settings-->Package Manager-->Advanced Settings中勾选Enable Pre-release Package之后 从Window-->Package Manager下左上方选择Add Package From git URL输入com.unity.progrids即可完成安装 后在Tools-->ProGrids-->ProGrids Window可以打开ProGrids插件 ProGrids主要是用于作为参考线 第一栏Snap Value是按照选定的距离进行拖拽移动

### 关于智能导航地图烘焙
在Window-->AI-->Navigation中打开面板 选中需要智能导航烘培的区域后勾选Navigation Static后在Navigation Area选择是否可以行走 在Bake中设置区域后点击Bake即可完成智能导航地图烘培 Bake设置区域时可以参考当前人物大小 给人物添加组件Nav Mesh Agent后调整Radius和Height到适合的大小后在Bake中将Agent Radius与Agent Height同步后Bake即可 同时也可以向地图中的障碍物添加Nav Mesh Obstacle障碍物组件 Shape可以更改描边 勾选Carve后即可按照当前物体大小切割物体 当物体移动时下方切割的地方烘培后玩家不可移动到该位置
