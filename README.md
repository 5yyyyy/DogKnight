# DogKnight
## 该说明仅针对此项目 此项目为端游3D RPG URP渲染管线
### Unity版本 2022.1.12  

### 关于3D默认渲染管线升级到URP管线
首先在Package Manager中安装Universal RP 之后在project窗口中Create-->Rendering-->URP Asset 然后在Edit窗口中Project Settings-->Graphics中添加新建的URP Asset 在Project Settings-->Quality也添加URP Asset 最后在Window窗口中Rendering-->Render Pipeline Converter窗口中下拉选择Build-in to URP后勾选Rending Settings和Material Upgrade后选择initialize Converters后Convert Assets即可

### 关于天空盒
在Window窗口中Rendering-->Lighting窗口下Environment-->Skybox Material更换需要的天空盒材质即可

### 关于阴影
URP Asset下更改Shadows的Max Distance可以调整渲染阴影的距离 更改Shadows的Cascade Count可以进行分级渲染 达到近实远虚的效果 更改Shadows的Split可以选择层级渲染距离 勾选Shadows的Soft Shadows可以使阴影模糊 更改Shadows的Normal Bias可以让影子有虚实变化 更改Lighting下的Shadow Resolution可以更改阴影分辨率 更改Quality的Anti Aliasing(MSAA)可以更改抗锯齿
