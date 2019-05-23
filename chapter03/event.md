### 事件

```xml
<view>
	<view class="btn" bindtap="testClick">Click</view>
</view>
```

```javascript
Page({
    testClick(e) {
        console.log(e)
    }
})
```

### 事件类型

#### 可捕获事件

* tap
* touchstart
* touchmove
* touchcancel
* touchend
* longpress
* longtap

#### 可冒泡事件

* touchstart
* touchmove
* touchcancel
* touchend
* tap
* longpress
* longtap
* transitionend
* animationstart
* animationiteration
* animationend
* touchforecechange