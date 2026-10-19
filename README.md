# iPhone 手机图像实验室（PWA）

在 Windows 上开发，使用 iPhone Safari 打开。页面通过 `getUserMedia` 直接调用 iPhone 后置摄像头，使用 OpenCV.js 在浏览器本机处理画面。

## 当前功能

- 实时摄像头预览和处理结果并排显示
- 灰度转换、灰度直方图
- 均值、中值、双边、高斯滤波
- 15×15 矩形结构元素形态学开运算
- Sobel、Laplace、Canny 边缘检测
- 可添加至 iPhone 主屏幕；静态页面外壳有 Service Worker 缓存

## 在 Windows 本地预览

1. 需要先将项目部署到带 HTTPS 的静态托管地址；iPhone Safari 的摄像头权限要求安全上下文。
2. 首次加载还需要网络下载 OpenCV.js。后续可以把对应版本文件放进项目再做离线打包。
3. 用 iPhone Safari 打开 HTTPS 地址，允许摄像头权限，即可使用。
4. 需要添加到主屏幕时，在 Safari 点“分享”→“添加到主屏幕”。

当前文件是可运行的前端原型，还没有部署到公网。PWA 不等同于 App Store 原生应用；若学校要求提交 Xcode 工程或 IPA，需要 Mac/Xcode 另行打包。形态学暂定为开运算，题目中的“15×15像素方块检测”仍需按老师具体定义确定算法。
