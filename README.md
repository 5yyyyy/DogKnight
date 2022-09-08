# DogKnight
## 该说明仅针对此项目 此项目为端游3D RPG URP渲染管线
### Unity版本 2022.1.12  

### 关于3D默认渲染管线升级到URP管线
首先在Package Manager中安装Universal RP 之后在project窗口中Create-->Rendering-->URP Asset 然后在Edit窗口中Project Settings-->Graphics中添加新建的URP Asset 在Project Settings-->Quality也添加URP Asset 最后在Window窗口中Rendering-->Render Pipeline Converter窗口中下拉选择Build-in to URP后勾选Rending Settings和Material Upgrade后选择initialize Converters后Convert Assets即可

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

### 关于ProBuilder绘制地面
在Window-->Package Manager下找到ProBuilder下载后需要Import对应的Samples 后在Tools-->ProBuilde-->ProBuilde Window可以打开ProBuilde插件 选择右上方Use Icon Mode 使用图形模式
