## WXML

> WXML（WeiXin Markup Language）是框架设计的⼀套标签语⾔，结合组件、WXS和事件系统，可以构建出⻚⾯的结构。



### 语法

```xml
<标签 属性名="属性值" 属性名="属性值"></标签>
```



#### Practice

```xml
<view class="m30" data-id="10">
	Hello,World!
    <view>
    	Thanks
    </view>
</view>
```

#### Present

![6D075047-7EBB-40F7-9ECB-E17C12593FD0](../assets/images/6D075047-7EBB-40F7-9ECB-E17C12593FD0.png)



### 特性

#### 数据绑定

##### Pratice

> Mustache方式

```xml
<!-- index.wxml -->
<view>
    <text>{{msg}}</text>
</view>
```

```javascript
// index.js
Page({
    data: {
        msg: "hello wxapp"
    }
})
```



##### Present

![D5D61922-0141-4CC0-954F-8F5AE6153D99](../assets/images/D5D61922-0141-4CC0-954F-8F5AE6153D99.png)

##### 属性绑定

```xml
<view>
	<text data-name="{{autherName}}"></text>
</view>
```

```javascript
Page({
    data: {
        autherName: "xiaocc"
    }
})
```



##### 运算符绑定

```xml
<view hidden="{{flag ? true : false}}">
	Hidden
</view>
```

```javascript
Page({
    data: {
        flag: false
    }
})
```

##### 字符串运算绑定、组合式绑定、扩展运算符绑定

#### 标签共同属性

| 属性名         | 类型         | 描述           | 注解                                 |
| -------------- | ------------ | -------------- | ------------------------------------ |
| id             | String       | 组件的唯一标识 | 保持整个页面唯一                     |
| class          | String       | 组件的样式表   | 在对应的wxss中定义的样式表           |
| style          | String       | 组件的内联样式 | 可以动态设置的内联样式               |
| hidden         | Boolean      | 组件是否显示   | 所有组件默认显示                     |
| data-*         | Any          | 自定义属性     | 组件上触发事件时，会发给事件处理函数 |
| `bind*/catch*` | EventHandler | 组件的事件     |                                      |



#### 列表渲染

```xml
<view>
	<block wx:for="{{items}}" wx:for-item="item" wx:key="index">
    	<view>{{index}}:{{item.name}}</view>
    </block>
</view>
```

```javascript
Page({
    data: {
        items: [
            {name: "法顶1"},
            {name: "法顶2"},
            {name: "法顶3"},
            {name: "法顶4"},
            {name: "法顶5"}
        ]
    }
})
```

![1558533419623](../assets/images/1558533419623.png)

#### 条件渲染

```xml
<view>谁取餐?</view>
<view wx:if="{{condition == 1}}">
张三
</view>
<view wx:elif="{{condition == 2}}">
李四
</view>
<view wx:else>
王五
</view>
```

```javascript
Page({
    data: {
        condition: Math.floor(Math.random()*3 + 1)
    }
})
```



#### 模板引用

```xml
<template name="tempItem">
<view>
    <view>收件人：{{name}}</view>
    <view>电话：{{mobile}}</view>
    <view>地址：{{address}}</view>
</view>
</template>

<template is="tempItem" data="{{...item}}"></template>
```

```javascript
Page({
    data: {
        item: {
            name: "cc",
            mobile: "13800138000",
            address: "北京市东城区东四十条"
        }
    }
})
```

