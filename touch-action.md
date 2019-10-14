### apply to https://github.com/mishe/blog/issues/160

> 今天看到有朋友说touch-action可以解决click 300ms延时；
> 
> 于是在caniuse上查了下兼容性，看下图：
> 
> ![image](https://user-images.githubusercontent.com/1996187/28506516-9a24ab74-705e-11e7-8075-435cbbc3ec1f.png)
> 
> 可以看到，现今的移动端页面兼容已经不是问题了，
> 
> * ios从9.3开始就支持了， 但只支持auto和manipulation
> * 安卓从5开始也支持，唯一需要关注的是安卓4.4和4.4.4这2个版本在项目中的占比。
> 
> 既然兼容问题不大了，那么看下touch-action的语法：
> 
> touch-action： auto | none | pan-x | pan-y | manipulation
> 
> * touch-action: auto | 浏览器会根据其支持的触控添加交互。比如x轴滚动、y轴滚动、双指缩放和双击。
> * touch-action: none | 浏览器禁用触摸交互。
> * touch-action: pan-x | 允许浏览器水平滚动，禁用垂直滚动及手势。
> * touch-action: pan-y | 允许浏览器垂直滚动，禁用水平滚动及手势。
> * touch-action: manipulation | 允许浏览器双方向滚动，也允许双指缩放；但忽略其他手势。
> 
> ```css
> html {
>     touch-action : manipulation
> }
> ```
> 
> 可以通过设置html的touch-action，之后项目就可以正常使用click了，并且附带的解决了点击穿透问题。因为click本身是不穿透的。
> 
> [在来看下MDN的文档，发现多了几个配置，具体如下：](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action)
> touch-action： auto | none | [ [ pan-x | pan-left | pan-right ] || [ pan-y | pan-up | pan-down ] || pinch-zoom ] | manipulation

