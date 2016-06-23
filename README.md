# GBAliScan
##仿写的类似支付宝二维码扫描的简单例子需要的自己看<br>
#前言:<br>
* 本demo简单的对二维码这一块做了一些简单的总结，采用的是系统提供的api框架，如果要支持ios6的话暂时这里不支持，这个api是从ios7之后才提供的，性能方面更优于之前的zbar和zxing。<br>
* 本demo是仿写的支付宝的大体效果，部分代码借鉴高少东的，并且在他的基础上添加了很多补充功能，并对他的代码做了一些优化。<br>
* 本demo是我最近在整理的oc教程篇中的其中一篇，以后还会陆续出一些oc上的教程，有的侧重功能有的侧重知识点的汇总，等完成oc的扫尾工作就开始学习和总结swift了<br>

###我最近也开了一个交流群，目前人数还不是很多，主要是提供大家一个学习ios开发的平台，欢迎大家的加入。群里有大神你们可以提问题（大神不是我，进群找那个叫张淼的，很牛逼）<br>

###群号：433060483欢迎加入组织,如果你觉得我的劳动对你有帮助请到右上角点颗星，算是对我劳动的回报。<br>


#直接上效果图吧：<br>

![](https://github.com/mokey1422/gifResourceOther/blob/master/GBAliScan.gif)
![](https://github.com/mokey1422/gifResourceOther/blob/master/2016-06-23%2022_43_35.gif)<br>
###补充说明：<br>
* 录制gif图的时候忘记了一步操作，就是二维码图片长按触发识别操作。这点在效果图上没有显示出来，自己看项目中的代码吧，很简单<br>
* 特别说明demo中用到的识别图片的api是苹果在ios8之后才开放出来的所以这里没有好的原生的解决方案的话就暂时用之前的三方替代一下吧推荐一个还一直在更新的库[ZXingObjC](https://github.com/TheLevelUp/ZXingObjC.git)，之前的zxing和zbar都已经断更很久了这个还一直在更新需要的自己去下载一下 <br>
* 还有的网友跟我说原生也可以生成二维码，我代码里是指直接用的libqrencode的代码，这个第三方的量级比较轻所以就直接用了，有强迫症的同学自己百度一下原生代码替换一下就可以了<br> 
* 关于横屏的适配问题，我看了一下微信的效果，貌似微信也不支持横屏，这个需求很小众就直接没有适配，有需要很平效果的比如pad的用户自己写一套布局吧，话说从出道到现在还没做过pad端的同学举个手<br>
* 这个例子只是简单的介绍二维码的基本使用，不是很严谨的框架，所以就不去维护了大家看着玩就好了，这套布局是根据高少东的布局思想做的，看上去很取巧，很奇葩你用图层工具看一下就知道了，哈哈 其实中间方形区域可以直接画出来不用实例化控件<br>

### 1.1更新说明<br>
* 知道有的同学比较懒我直接把ios8系统之前读取照片中的推荐的第三方加进去了并且有注释，自己更新一下<br>
* 但是这个第三方的对于一些特殊的二维码的识别率没有系统自带的识别率高这是一个问题<br>
* 还是有点小问题，暂时就这样吧，代码注释很清楚自己看吧<br>

###1.2更新说明<br>
* 感谢陈密同学分享的二维码系列，特此分享给大家并纠正了陈密同学的一个内存bug，在使用原作者的demo中会出现内存不释放的问题，予以纠正。<br>
* 添加了很多二维码的新玩法，并且尝试解决识别特殊二维码经常会失败的问题（未完）<br>
* 替换之前通过c算法来生成二维码的方法，采用苹果系统原生的CIFliter来生成二维码。
