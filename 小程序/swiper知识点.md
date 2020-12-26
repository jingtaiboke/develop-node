  1轮播图外层容器 swiper

  2每一个轮播项 swiper-item

  存在默认样式

  width:100%

  height:150px image mode 存在默认宽高 320*240

  swiper无法实现内容由高度撑开



  先找原图宽高 等比例 给swiper 定宽高

  900*367

  swiper宽度 / swiper高度 = 原图宽度/原图高度

  swiper高度 = 原图宽度/原图高度 * swiper宽度



  autoplay: 自动轮播

  interval: 间隔时间

  circular: 衔接循环轮播

  indicator-dots 显示 指示器(分页器)

  indicator-color: 未选中的颜色

  indicator-active-color: 选中的颜色

```
<swiper autoplay interval="1000" circular indicator-dots indicator-color="#0094ff" indicator-active-color="#ff150f">
    <swiper-item>
        <image mode="widthFix" src="http://tarrowtmo.cn/animation/loading.webp"/> 
    </swiper-item>
    <swiper-item>
        <image mode="widthFix" src="http://tarrowtmo.cn/animation/bird.webp"/> 
    </swiper-item>
    <swiper-item>
        <image mode="widthFix" src="http://tarrowtmo.cn/animation/hover.webp"/> 
    </swiper-item>
</swiper>

```

