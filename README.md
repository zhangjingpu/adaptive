# adaptive
H5端自适应框架

###使用方法：
```javascript
<script src="js/adaptive.js"></script>
<script>
    window['adaptive'].desinWidth = 640;// 设计图宽度
    window['adaptive'].baseFont = 18;// 没有缩放时的字体大小
    window['adaptive'].init();// 调用初始化方法
</script>
```
然后在css中设置相应样式即可：
```css
.main-info {
    height: 0.88rem;
    padding-bottom: 0.24rem;
}
.fund-info {
    position: relative;
    font-weight: normal;
    padding: 0.2rem 0;
    padding-right: 1.7rem;
    padding-left: 0.23rem;
    font-size: 0.32rem;
    line-height: 1;
}
```
###adaptivejs原理：  

    利用rem布局，根据公式  
    
    html元素字体大小 = document根节点(html)宽度 * 100 / 设计图宽度  
    
    设置html元素的font-size,然后根据设计图大小/100即为css大小。  
    比如一个div设计图宽度为89px,那么在css中我们可以这样书写：width:0.89rem;  
    如果是文字，我们也建议使用rem。  
    
    对于iphone的retina高清显示屏，我们做了缩放处理，以达到最佳显示效果。  
    
###注意：如果设计图宽度大于document的宽度，0.01rem将小于1px,故如果设计图是1px,在css中仍然用1px显示。
 可用的全局变量：window.devicePixelRatioValue 当前页面设置的设备像素比
