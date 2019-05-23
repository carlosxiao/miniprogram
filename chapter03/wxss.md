## WXSS

> WXSS (WeiXin Style Sheets)  是⼀套样式语⾔，⽤于描述WXML 的组件样式 



### 尺寸单位 RPX

#### 设备像素(device pixels)

> 设备能显示的物理单位

#### CSS像素(CSS pixels)

> web 编程中的逻辑像素

#### PPI/DPI(pixel per inch)

> 每英寸所拥有的像素数目，数值越高代表显示屏能以更高的密度显示

#### DPR(Device pixel ratio)

> 设备像素与css像素之比

### 样式导入

```xml
<view class="container">
	Hello WXSS
</view>
```

```css
@import './common.wxss'
    
.container {
    color: red
}

/** common.wxss **/
.container {
    border: 1px solid #01F;
}
```



### 内联样式

```xml
<view style="width:500rpx;height:30px;background-color:{{pCorlor}}">
    Heiil
</view>
```

```javascript
Page({
    data: {
        pColor: red
    }
})
```



### 选择器

* 选择器权重
  * element
  * .element
  * #element
  * style
  * !important

#### 类选择器

#### ID 选择器

#### 元素选择器

#### ::after

#### :before