## Android自定义小红点BadgeView

想全局统一个小红点样式，总是改了这个忘了其他的，而且小红点格式各样，总是满足不了自己的需求，所以心血来潮自己自定义View onDraw了一个。

可前往查看[GitHub源码](https://github.com/SkylerHu/BadgeView).

效果就是这样....

![BadgeView_preview.gif](http://7xpdkx.com1.z0.glb.clouddn.com/gif/blog/BadgeView_preview.gif)

一定要记得在`attrs.xml` 项目中添加
```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <declare-styleable name="BadgeView">
        <attr name="iconSrc" format="reference"/>
        <attr name="iconWidth" format="dimension"/>
        <attr name="iconHeight" format="dimension"/>
        <!--若是icon是正方形的,可直接设置这个参数-->
        <attr name="iconSize" format="dimension"/>

        <attr name="text" format="string"/>
        <attr name="textSize" format="dimension"/>
        <attr name="textColor" format="color"/>

        <attr name="badgeNum" format="integer"/>
        <!--是否显示数字, 为false时只显示小红点; 没有数字时,小红点的大小通过badgeSize设置-->
        <attr name="showNum" format="boolean"/>
        <attr name="badgeBackgroundColor" format="color"/>
        <!--限制设置小红点的大小不能超过数字显示模式(代码中也做了限制); 显示在文字模式大小的左下角;-->
        <!-- 不显示数字时, 小红点的大小, 不包括边线-->
        <attr name="badgeRedSize" format="dimension"/>
        <attr name="badgeNumSize" format="dimension"/>
        <attr name="badgeNumColor" format="color"/>
        <!--若小红点有边缘线,加上边缘线-->
        <attr name="badgeBorderColor" format="color"/>
        <attr name="badgeBorderWidth" format="dimension"/>
        <!--badge相对于主体右上角的相对位置, 重叠的部分的大小; 可以设置负值-->
        <!--默认是( badgeHeight/2 ), 正好覆盖一个角-->
        <attr name="badgeBottom" format="dimension"/>
        <attr name="badgeLeft" format="dimension"/>
        <!-- 有些设计要求未读前面加"+", (至少我们设计师这么设计) 显示成 +1/+34/+99-->
        <attr name="badgeNumPre" format="string"/>
    </declare-styleable>
</resources>

