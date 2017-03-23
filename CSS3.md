# 选择器
## 后代级别
* :nth-child(n)---选择的当前元素在父元素中要作为子元素出现，他是第n个孩子（在乎其他元素）
* :first-child---作为第一个子元素出现
* :last-child---作为最后一个子元素出现
* :nth-last-child(n)---从最后一个子元素开始计数。
* :only-child---作为独生子出现
* :empty---选中没有任何子级的元素（包括空的文本节点）
* :nth-of-type(1)---要选中的元素在同类型元素中的第一个

## 同辈元素
* :nth-of-type(n)---作为同辈元素中的第n个（不在乎其他元素）
* :nth-last-of-type(n)---从后往前计数
* :first-of-type---作为第一个兄弟元素出现
* :last-of-type---作为最后的兄弟出现

## 伪类
* :hover---鼠标移入
* :after---一个元素后面的部分
* :before--前面的部分
* :first-letter---元素的第一行文字
* :first-line---元素的第一个文字
* :focus---获得焦点
* ::selection--浏览器选中文字的样式

## 属性选择器
* [affr]---具有某个属性
* [affr=val]---具有指定值的属性
* [affr*=val]---包含有指定的值的一部分的属性
* [attr^=val]---属性值的开头和指定的值一样的元素
* [attr$=val]---属性值的结尾头和指定的值一样的元素

# 边框模型
## 圆角
* border-raduis:圆角的半径（%/px/em）
* 参数的顺序依次是：左上，右上，右下，左下（顺时针的）

## 阴影
* box-shadow:x y blur color [inset],[x y blur color inset]
    * x：阴影在x轴的偏移量
    * y：阴影在y轴的偏移量
    * blur：阴影的模糊程度
    * color：阴影颜色
    * inset：内阴影，不写默认outset外阴影

## 图片边框
* border-image-source:url(../images/.);//图片的路径
* border-image-width:30px;//图片边框的宽度
* border-image-slice:33.33%;//与原图裁切比例
* border-image-repeat:round;//平铺方式
* border-image-outset:10px;//扩展/图片边框的偏移量

## 字体图标的实现步骤
1. 创建字体
    * 利用svg制作矢量图
    * 将svg格式的图片生成字体
        * 阿里巴巴平台
        * 字体生成器
        * 字体格式
2. 将创建的字体引入到css页面当中
    * @font-face：引入字体
    * content:"\e61a"
3. 给指定的元素指定相应的字体
    * 知道指定的字体对应的代码是什么
    * 不知道指定的字体对应的代码
        css中用：before

## 过度：从a点到b点,所有变化;
* transition：属性 时间 [运动方式] [等待时间],[属性 时间 [运动方式] [等待时间]]
* 时间单位：s/ms
    * transition-property: width;指定那个属性去动画
    * transition-duration: 3s;指定动画持续的时间
    * transition-timing-function:cubic-bezier(1,1,1,1);运动方式
    * transition-delay: 2s;等待时间
one.addEventListener(webkitTransitionEnd,function(){})监测动画是否运行完成
## 颜色和透明度
* rgba()
    rgb分别表示红绿蓝0-255
    a透明度0-1
* hsl
* hsla
* 透明色 
	* background:transparent;
* 工业界的颜色标准
    * background-color:hsla(120,65%,75%,0.3);
* 线性渐变
    * background: linear-gradient([角度],color,color-stop,color color-stop,color color-stop);
    
    * 简单的线性渐变：
    ```
    （默认渐变方向从上到下）
	    background: -webkit-linear-gradient(red, blue); /* Safari 5.1 - 6.0 */
	    background: -o-linear-gradient(red, blue); /* Opera 11.1 - 12.0 */
	    background: -moz-linear-gradient(red, blue); /* Firefox 3.6 - 15 */
	    background: linear-gradient(red, blue); /* 标准的语法（必须放在最后） */ 
	//从左到右的渐变:
		background: -webkit-linear-gradient(left, red , blue); /* Safari 5.1 - 6.0 */
	    background==: -==o-linear-gradient(right, red, blue); /* Opera 11.1 - 12.0 */
	    background: -moz-linear-gradient(right, red, blue); /* Firefox 3.6 - 15 */
	    background: linear-gradient(to right, red , blue); /* 标准的语法（必须放在最后）*/
	```
	* 渐变位置：百分比指定
		background: linear-gradient(to right,red 0%,blue 30%,pink 70%,green );
	* 指定方向
        * rad弧度
        * deg角度
* 径向渐变
    *  background: radial-gradient([[形状] [半径] at [x,y]],color color-stop);
        * background: radial-gradient(circle at 10px,red 0%,blue 30%,pink 70%,green );
        * 形状
            * circle:圆;
            * ellipse:椭圆;
        * background: radial-gradient(ellipse 10px 10px at 10px,red 0%,blue 30%,pink 70%,green );
* 重复渐变
	* background: repeating-radial-gradient(red, yellow 10%, green 15%);

## 背景模块
* background-image:img1,img2;
    * 可以设置多个背景
* background-size:
    > 设置背景的尺寸

    * cover(小比例为基准)
    * contain(比例大的为基准)
* background-origin:
    > 设置背景填充的原点

    * border-box;//从边框
    * content-box;//正常
    * padding-box；//从内边距
* background-clip:
    > 裁切

    * border-box;背景被裁剪到边框盒
    * content-box;背景被裁剪到内容框
    * padding-box；背景被裁剪到内边距框。 

* background-attachment:fixed;

# 图形图像转换
	WebGl:
	css3之前,浏览器里面是不能处理图形图像的
		1 必须对图形图像左大量的运算处理
		2.浏览器并不具备处理图形图像的能力
		3.硬件的限制,并不能流畅的处理
	
	图形图像的转换
		1平移
		2旋转
		3缩放
		4斜切
# css中hover用法
    .box:hover .btn{...}
# window最小化失去焦点问题
    window.onblur=function(){失去焦点时清除时间函数}
    window.onfocus=function(){获得焦点时开启时间函数}












































