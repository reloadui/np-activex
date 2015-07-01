## 当控件的某一级display设为none时，控件无法加载 ##

如
```
<div id="parent" style="display:none">
  <object id="obj" xxxxxx></object>
</div>
```
此时obj将不会加载。重新显示时控件会重新初始化。
因此，在招行中，若切换了登录类型，所有设置会失效，包括加密时的key。而交通银行的commit控件是显示为none的，无法获得提交控件。

目前的解决方案：
1. HOOK display设为none的过程，将此操作改为"width=0 height=0"，但目前没找到hook点
2. 使用一个网页级的manager插件，每次创建、销毁均由此manager完成。不过实现复杂，manager控件的创建时间很难掌握，且所有调用均需要转发。