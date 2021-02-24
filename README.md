#### 使用说明文档
> 如果该库对你有帮助，请动动你的小手指，给个star🤩   

滑动解锁控件，kotlin语言开发，可应用于锁屏，滑动控制、来电接听等页面场景。
  

- [x] 支持配置背景颜色、圆角大小
- [x] 支持背景跟随滑动距离伸缩
- [x] 支持配置滑块为圆形/方形
- [x] 支持配置滑块背景颜色、图标、内边距
- [x] 支持字体颜色、大小、流光效果配置
- [ ] 支持配置滑块显示文字/图片




#### 效果预览
<img src="https://raw.githubusercontent.com/Leo199206/SlideUnlock/main/image/device-2021-02-24-115028.gif" width="300" heght="500" align=center />


#### 依赖
+ 添加maven仓库配置到项目根目录gradle文件下

```
allprojects {
    repositories {
        maven { url 'https://jitpack.io' }
    }
}
```

+ 添加以下maven依赖配置到app模块，gradle文件下

```
implementation  'com.github.Leo199206:SlideUnlock:1.0.0'
```

#### 添加到布局

```
      <com.slide.unlock.view.SlideUnlockView
          android:id="@+id/slide_circle"
          android:layout_width="250dp"
          android:layout_height="50dp"
          android:layout_marginBottom="20dp"
          android:padding="2dp"
          app:layout_constraintBottom_toTopOf="@id/slide_square"
          app:layout_constraintLeft_toLeftOf="parent"
          app:layout_constraintRight_toRightOf="parent"
          app:resilienceDuration="500"
          app:thumbShape="CIRCLE"
          app:thumbBgColor="@android:color/white"
          app:thumbPadding="10dp"
          app:thumbSrc="@drawable/ic_arrow"
          app:thumbSrcTint="#35B303"
          app:thumbWidth="60dp"
          app:trackBgColor="#64000000"
          app:trackRoundCorner="50dp"
          app:unlockLockText="滑动解锁"
          app:unlockLockTextColor="@color/black"
          app:unlockLockTextSize="16sp" />

   <com.slide.unlock.view.FlexibleSlideUnlockView
        android:id="@+id/slide_ios_circle"
        android:layout_width="250dp"
        android:layout_height="50dp"
        android:padding="2dp"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toBottomOf="@id/slide_square"
        app:resilienceDuration="500"
        app:thumbShape="CIRCLE"
        app:shineEffect="true"
        app:thumbBgColor="@android:color/white"
        app:thumbPadding="10dp"
        app:thumbSrc="@drawable/ic_phone"
        app:thumbSrcTint="#35B303"
        app:thumbWidth="60dp"
        app:trackBgColor="#64000000"
        app:trackRoundCorner="50dp"
        app:unlockLockText="滑动以接听"
        app:unlockLockTextColor="@color/black"
        app:unlockLockTextSize="16sp" />
```

+ 代码配置

```

  lockView.setSlideUnlockCallback(object: OnSlideUnlockCallback{
            override fun onSlideUnlock(success: Boolean) {
                //success为true时，解锁成功，false解锁取消/失败
            }
        })

```


#### 已定义样式属性

| 属性  | 说明 |
| --- | --- |
| trackBgColor | 背景颜色 |
| trackRoundCorner | 背景圆角大小 |
| thumbShape | 滑块形状，CIRCLE为圆形，SQUARE为方形 |
| thumbBgColor | 滑块背景颜色 |
| thumbSrcTint | 滑块图标颜色 | 
| thumbSrc | 滑块图标图片 | 
| thumbWidth | 滑块宽度，仅方形滑块有效，圆形滑块宽高默认为去除内边距的控件高度 |
| resilienceDuration | 取消解锁，滑块回弹动画时长 |
| unlockLockText | 解锁提示 |
| unlockLockTextSize | 解锁提示文字大小 |
| unlockLockTextColor | 解锁提示文字颜色 |
| unlockLockTextShineColor | 解锁提示文字，流光效果颜色，仅在shineEffect为true时生效 |
| shineDuration | 解锁提示文字流光效果，动画时长 |
| shineEffect | 是否开启解锁提示文字流光效果 |


#### LICENSE
SlideUnlock is under the Apache License Version 2.0. See the [LICENSE](https://raw.githubusercontent.com/Leo199206/SlideUnlock/main/LICENSE) file for details.