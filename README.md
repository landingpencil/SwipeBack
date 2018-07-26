# SwipeBack
SwipeBackLayout侧滑关闭页面

## 效果预览
![](https://github.com/bjchenxz/SwipeBack/raw/master/gif/1.gif)
## 使用方式
### build.gradle文件
```
implementation 'com.cxz:swipeback:1.0.1'
```
### Activity继承SwipeBackActivity
```
public class MainActivity extends SwipeBackActivity{
    private SwipeBackLayout mSwipeBackLayout;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
	...
	mSwipeBackLayout = getSwipeBackLayout();//获取SwipeBackLayout
    }
}
```
### 设置滑动关闭的方向
```
mSwipeBackLayout.setEdgeTrackingEnabled(SwipeBackLayout.EDGE_LEFT);
```
### 添加滑动事件监听
```
mSwipeBackLayout.addSwipeListener(new SwipeBackLayout.SwipeListener() {
    @Override
    public void onScrollStateChange(int state, float scrollPercent) {
    }
    @Override
    public void onEdgeTouch(int edgeFlag) {
        vibrate(VIBRATE_DURATION);
    }
    @Override
    public void onScrollOverThreshold() {
        vibrate(VIBRATE_DURATION);
    }
});
```
