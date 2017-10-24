# html-loading
网页加载loading
### 方法一
demo1
```js
// 定时器
$(function(){
  var loading='<div class="loading"><div class="pic"></div></div>'
  $("body").append(loading);
  //定义3秒后隐藏loading
  setInterval(function(){
    $(".loading").fadeOut();
  },3000)
})
```

### 方法二
demo2
```js
// 通过加载状态时间制作进度条
// document.onreadystatechange 页面加载状态改变时的事件
// document.readyState 返回当前文档的状态
// readyState 的状态有：
// uninitialized  -还未开始载入
// loading        -载入中
// interactive    -已加载，文档与用户可以开始交互
// complete       -载入完成


// 通过加载状态来显示进度条
document.onreadystatechange=function(){
  if(document.readyState=="complete"){
    $(".loading").fadeOut();
  }
}
```

### 方法三
demo3
增加css3动画loading效果
```
<link rel="stylesheet" type="text/css" href="css/loading.css">
<div class="loading lds-css ng-scope">
  <div style="width:100%;height:100%" class="pic lds-pacman">
    <div>
      <div></div>
      <div></div>
      <div></div>
    </div>
    <div>
      <div></div>
      <div></div>
    </div>
  </div>
</div>
```
```js
// 通过加载状态来显示进度条
document.onreadystatechange=function(){
  if(document.readyState=="complete"){
    $(".loading").fadeOut();
  }
}
```

### 方法四
demo4  定义在头部的进度条
```css
.loading{
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: #fff;
  z-index: 100;
}
.loading .pic{
  width: 0%;
  height: 5px;
  border: 1px solid #900;
  position: absolute;
  top: 0;
  left: 0;
  background-color: red;

}
```
```js
// 通过加载状态来显示进度条
document.onreadystatechange=function(){
  if(document.readyState=="complete"){
    $(".loading").fadeOut();
  }
}
```
```js
$(".loading .pic").animate({width:"10%"},100)
```
```js
$(".loading .pic").animate({width:"30%"},100)
```
```js
$(".loading .pic").animate({width:"80%"},100)
```
```js
$(".loading .pic").animate({width:"100%"},100)
```


