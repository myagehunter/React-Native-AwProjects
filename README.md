# React-Native-AwProjects
React Native (简称RN)是Facebook于2015年4月开源的跨平台移动应用开发框架，是Facebook早先开源的JS框架 React 在原生移动应用平台的衍生产物，支持iOS和安卓两大平台。

1. 首先下载node.js 安装包 配置环境 https://nodejs.org/zh-cn/download/
2. 配置完成之后到dos窗口输入npm -v ,出现版本号说明安装node.js成功
3. 之后输入npm install -g react-native-cli 就可以安装我们react-native工具
4. 成功之后输入react-native -help 可以看到支持的react-native 所支持的命令
5. 然后我们可以通过init 可以初始化项目 npx react-native init AwesomeProject(注：看最新官网文档不然坑很多) https://reactnative.cn/docs/getting-started
6. 这样React-native就可以从vpn服务器下载依赖包，这里我们需要设置镜像服务器，在node.js安装根目录
npm里找到npmrc 打开添加registry=https：//registry.npm.taobao.org （https://www.cnblogs.com/sghy/p/6840925.html）配置镜像服务器，这样创建的时候只需要
到镜像服务器里下载依赖工具包，就可以大大提高初始化速度
7. 这时候直接运行会有个坑，会报android ReactNative之Cannot find entry file index.android.js in any of the roots错误，在react native以前的版本，index.android.js与index.ios.js是分开的两个文件
、在最新版本中这两个文件合并成index.js一个文件了，报错原因在根目录没找到两文件
8. 解决方法： https://www.jianshu.com/p/55357f9d273b
 创建目录：mkdir android\app\src\main\assets之前记得cd AwesomeProject目录下
 创建两个文件 npx react-native bundle --platform android --dev false --entry-file index.js --bundle-output         android/app/src/main/assets/index.android.bundle --assets-dest android/app/src/main/res/
这时候再运行就不报错了
9.  运行项目如果报错记得重新安装jdk，可能路径配置不对。
