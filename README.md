## 微信小程序，踩坑总结
#### 2018-09-11
* [cover-view文字显示不全](https://developers.weixin.qq.com/community/develop/doc/0004064a4d00108138a6ac12357000)
* `wx.getSystemInfoSync()` 有些安卓机获取不到信息
* `cover-view` [需要紧跟在需要被覆盖的原生组件后面写，不然无法覆盖](https://developers.weixin.qq.com/community/develop/doc/00006a04b60a280fd6175d83e5b000)
* `cover-view` [iOS上动画位置可能会不准确](https://developers.weixin.qq.com/community/develop/doc/000660d609cb28492f179dae951800)
* `cover-view` `text-decoration` 真机上无效
* [video视频播放按钮被poster 图片遮挡住了](https://developers.weixin.qq.com/community/develop/doc/0002249d088df080f107f3b255bc00)
* [input输入框内容无法删除](https://developers.weixin.qq.com/blogdetail?action=get_post_info&docid=000222565dc9e87a6c273d9785b800&commentid=0000c6a44646d0d17d271e5a85ac&parent_commentid=000aa40d1649f8817b27fb1ae51c&token=1682505759&lang=zh_CN)
* [自定义组件通过列表渲染，内部数据会相互干扰](https://developers.weixin.qq.com/community/develop/doc/000aa21667c9a873a457961a05b800)
* [循环渲染，里面包含video时，有时候video会被渲染到其他位置](https://developers.weixin.qq.com/community/develop/doc/000ca8cfed4d18c59a57d4e4156800)
* [画布 drawImage 时图片的显示大小出错](https://developers.weixin.qq.com/community/develop/doc/000422ba6d4f18069f3678f1656000)
* [cover-view嵌入button按钮无法open-type](https://developers.weixin.qq.com/community/develop/doc/0004ea1903cdc07cbb17c32e956000)
* [iOS 不能显示webp 图片](https://developers.weixin.qq.com/community/develop/doc/000aa668604fc855dc3759eba51800?highLine=webp)
* 安卓手机授权之后，就算删除了小程序，重新进去之后，还是不用授权；苹果手机授权之后，删除了小程序，重新进去，还是要授权；
* chooseAddress有部分机型success会回调2次
* 分享图片链接有中文，IOS无法加载
* cover-view下的cover-image 有时候图片显示不出来，但是位置占了
* [getImageInfo 安卓不能获取到本地图片](https://developers.weixin.qq.com/community/develop/doc/00060ca8578430698b370c5fb56000?highLine=getImageInfo%25E4%25B8%258D%25E8%2583%25BD%25E5%258A%25A0%25E8%25BD%25BD%25E6%259C%25AC%25E5%259C%25B0%25E5%259B%25BE%25E7%2589%2587)
* canvas 不能画base64 图片，需要后台返回二进制流，前端download下来 `wx.downloadFile()` 才能画到canvas上面。
* [cover-view 组件在安卓机器上无法上下滑动 之后滑动cover-view](https://developers.weixin.qq.com/community/develop/doc/00006a05e60ea0701f47838365b000?highLine=custom-cache)
* iOS视频链接出现中文，会导致视频不能播放，需要手动 `encodeURI()`
* iOS视频可能会出现播放一段之后卡死，需要加上 `custom-cache="{{false}}"`
* 有些安卓机，API请求参数中不能带有空格，需要手动 `encodeURI()`
* `console` 打印太多内容，可能会导致真机页面不显示
* [video组件加载完成出现横竖两个叠加图片](https://developers.weixin.qq.com/community/develop/doc/0006e636da09c0f360c6acb0a5a400)
* [input在底部时，会被弹出的键盘遮住](https://developers.weixin.qq.com/community/develop/doc/000ac25c670028ae64e6cf8c251400)
* 图片设置 `mode="widthFix"` 当图片大小和CSS设计的高度相差较大时，加载会闪烁一下
* `cover-view` [fixed 定位时，在iOS中，下拉刷新会拉动cover-view 的位置，并且回不去原来位置](https://developers.weixin.qq.com/blogdetail?action=get_post_info&lang=zh_CN&token=487308417&docid=000e6891444860592f079328f5bc00) 已修复
* wxs 使用正则不能直接使用双斜杠写法 `/[abc]/g` ，需要通过 `getRegExp()` 方法得到一个正则，不能使用 `new RegExp()` 和 `new Date()`
* 小程序中 `button` 的边框是用 `after` 实现的，所以说想要去除button上的边框需要设置 `:after{border：none}`。
* [wx.getStroage 异步在iOS系统下是同步执行](https://developers.weixin.qq.com/community/develop/doc/000ce6b95f4c90ee8e57e001751c00?highline=getSt)
* iOS 某些emoji字符导致整个canvas不显示
* 自定义组件，有些CSS伪类不支持，组件会直接不显示
* 自定义组件，外部修改内部样式，只能通过传class，但是直接在外部写 标签名也能应用到内部标签上
* ...

