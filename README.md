# 微信小程序示例：一奇相册（正在审核中）

## 首页图片演示
![图片名称](https://img-blog.csdnimg.cn/20200502150357241.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzE5NDUwMDc1,size_5,color_FFFFFF,t_30) 


## 程序介绍
学习node.js顺便接的单，相比自己以前写的，这次相对来说比较规范，用于个人相册展示，适合微商，有客服联系，无需后台管理系统，小程序上直接进行管理，没有登录账号只拥有查看功能。

## 功能介绍
1.首页进行相册展示，采用分页
2.列表页面以文字形式进行分类，管理员可进行添加，修改和排序
3.每个列表下有多个相册，管理员可进行添加，修改和排序
4.每个相册有多张图片，有小图和大图模式进行切换
5.相册中可以长按图片进行选择删除和设为封面
6.相册可以进行分享
7.我的页面有管理员登录，联系客服等功能

## 开发语言
前端：uniapp
后端：node.js
数据库:mysql5.7
图片存储：七牛云

## 开发软件
HBuilder X

## 下载教程
`
git clone https://github.com/yiqia/Album.git
`
## 安装教程

1.上传server文件夹到服务器

2.修改config/conn.js文件里的mysql配置信息
`
var pool = mysql.createPool({
    host: '127.0.0.1',//数据库地址
    user:'root',//数据库账号
    password:'root',//数据库密码
    database:'album'//数据库名
});
`
3.修改config/qiniu.js文件里的七牛云配置信息
`
qiniu_sdk.conf.ACCESS_KEY = "xxx"
qiniu_sdk.conf.SECRET_KEY = "xxx"  
qiniu_sdk.conf.url="xxxx"  //七牛云绑定域名
// 要上传的空间名
const bucket = "xxxx"
`

4.使用命令或者PM2管理器运行sever文件夹下的main.js
`
node main.js
`

5.若安装失败，可能是没有依赖原因，需要先安装依赖
`
npm install
`

安装完成后重新执行第4的步骤运行

6.导入mysql数据库
如果导入失败，尝试一下用工具连接数据库，使用工具导入。

7.修改前端接口请求地址，改成自己服务器的接口地址，/App.vue
要注意小程序必须要使用https，node.js运行起来是以端口号的形式访问，所以需要用反向代理，把ip指向域名。
`
globalData: {
			//url: 'http://192.168.1.12:10001/'
			url: 'https://ablum.q05.cc/'
		}
`

8.使用HBuilder X 发布到微信小程序即可

**最后有什么不懂的可以问我哦
qq330729121**

