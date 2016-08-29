/* 前端产品文档*/
＊本文档供前端开发人员使用，供内部人员参考
》更新日志请见https://gitshell.com/Triploc/App/tree/master/
＃＃目录（index）

＃＃＃克隆项目
＃执行下面的步骤
git clone https://gitshell.com/Triploc/com-qiudao-cordova-umeng-analytics.git
git clone https://gitshell.com/Triploc/cordova-plugin-wechat-develop.git
git clone https://gitshell.com/Triploc/mobile-website.git
git clone https://gitshell.com/Triploc/cordova-plugin-leancloud.git
git clone https://gitshell.com/Triploc/cordova-plugin-easemob.git
git clone https://gitshell.com/Triploc/cordova-plugin-alipay-master.git
git clone https://gitshell.com/Triploc/CMS.git
git clone --recursive https://gitshell.com/Triploc/App.git
cd App （进入改项目目录下）
git submodule init （确保andorid和iOS初始化，可查看是否存在文件）

----安装Node.js

－－安装开发环境
npm install -g cnpm (淘宝镜像，加快npm下载速度)
cnpm -v  --检测版本

－－以后安装插件使用cnpm install 即可

--安装移动端需要的框架插件
cnpm install -g express  --为避免报错，需安装这步
cnpm install -g  ionic 
cnpm install -g  vordova 

--安装iOS真机测试环境
下载sdk，Xcode
npm install -g ios-sim
npm install -g ios-deploy

＊＊＊进行build
ionic  build iOS android 

＊＊＊打开模拟器
ionic  emulate ios android

＃＃＃自动化构建
本项目使用gulp进行外部包和依赖的管理
》gulp官方网站：http：／／gulpjs.com 
安装完成后，执行npm install 下载gulp以及相关的组件

本项目自动构建的内容包括：
＊创建本地服务器：http://localhost:8100/#/tab/home  
＊监听项目修改主要包括:
   监听App/scss文件夹，执行gulp后，将文件自动打包到www／css／style.min.css 目录下，最后通过执行gulp－useref，将所有文件合并打包到www/dist/dist_css中，在页面中调用改文件即可
   监听www/js文件，执行gulp之后，将文件打包到www/dist/dist_js/app/app.js ||  www/dist/dist_js/app/templates.js 
＊常用的gulp task
   ＊执行命令 gulp：启动服务器
  
＃＃＃启动服务器：
ionic  serve   －－打开app首页

－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－

＃＃＃产品文档结构（app）
＊hooks／         ［ionic执行相关的事情时会运行的脚本］
    _after_platform_add/
    _after_prepare/
    _before_platform_add/
    _before_prepare/
＊node_modules/   ［node依赖］
＊platforms／     ［安卓和iOS下的平台］
    _android/
    _ios/
*plugins/         [插件配置]
＊resources／     ［资源加载］
＊scss/           [需要在里面写页面的样式]
＊www/            
    _bower_components    [bower包依赖下载]
    _css                 [gulp打包压缩之后的样式文件]
    _dist                [缓存文件，最终全部页面均通过调用该文件里的项目]
    _js                  [我们写的脚本文件]
    _jsons               [数据交互使用的数据]
    _lib                 [第三方的框架和资源]
＊templates／            [页面，最终打包成js文件，供调用]
＊test／
   _bower.json             [bower数据]
   _cordova.js
   _index.html              ［主页面］
   _main.html
   _redirect.html           ［跳转页面］
   _test.css

＊＊其它结构说明待定

－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－

### 文章更新操作流程

先下载FTP        －－将本地站点与远程站点联系起来
下载sourcetree   －－－将本地项目提交托管到gitshell里面 ，下载地址：http://www.cnblogs.com/jtjds/p/5305902.html

＊＊＊本项目托管在两台服务器上，主要是放置需要加载的静态资源
主机：114.215.208.94   用户：zuihuiyou 密码：zuihuiyou2014
主机：120.26.122.22    用户：zuihuiyou 密码：zuihuiyou2014
主机：192.168.1.17     用户：root  密码： zuihuiyou2014/zuihuiyou123  －－点击下载json文件
文字编辑所使用的工具地址：http://192.168.1.17:3888/#/home －－写好后自动生成json文件

－－将www／jsons/article_160712_*********.json 里面的最新文件复制articleV4.json 和 articleV5.json

－－本地测试 ：js/HomeCtrl.js  js/ContentService.js  

－－本地完成后，将修改后的资源提交到FTP服务器上

先将文章提交到



