# 快应用入门

## 项目搭建
## 安装Nodejs
1. 需安装6.0以上版本的nodejs，请从NodeJS官网下载，推荐v6.11.3 LTS
2. 注意: 不要使用8.0.*版本．这个版本内部ZipStream实现与node-archive包不兼容，会引起报错，注意！！！不是8.0.*以上版本不行，例如我Nodejs版本为v8.2.1也是能正常开发，不要看到自己Node版本大于8.0以上就重装

## 安装hap-toolkit
### 通过npm仓库安装，在命令行中执行以下命令：
```
	npm install -g hap-toolkit
```
### 在命令行中执行hap -V会输出版本信息表示hap-toolkit安装成功，如下命令所示：
```
	hap -V
	0.0.26
```

## 创建第一个快应用项目
1. 在你要创建项目的路径输入命令行 hap init <ProjectName>，点击两次回车，当前路径就创建了你项目的文件夹
```
	hap init MyQuickApp //创建一个名为MyQuickApp的项目，这里点击两次回车
	
	cd MyQuickApp   //创建成功，进入项目根目录

	npm install 	//安装依赖，当前操作要在项目根目录执行

	npm run build	//编译打包项目，项目根目录下会生成文件夹：build、dist
```
- build：临时产出，包含编译后的页面js，图片等
- dist：最终产出，包含rpk文件。其实是将build目录下的资源打包压缩为一个文件，后缀名为rpk，这个rpk文件就是项目编译后的最终产出

2. 这个项目已经包含了项目配置与简单页面的初始代码，项目根目录结构如下：
```
├── node_modules
├── sign                      rpk包签名模块
│   └── debug                 调试环境
│       ├── certificate.pem   证书文件
│       └── private.pem       私钥文件
├── src
│   ├── Common                公用的资源文件和组件文件
│   │   └── logo.png          manifest.json中配置的icon
│   ├── Demo                  页面目录
│   |   └── index.ux          页面文件，文件名不必与父文件夹相同
│   ├── app.ux                APP文件（用于包括公用资源）
│   └── manifest.json         项目配置文件（如：应用描述、接口申明、页面路由等）
└── package.json              定义项目需要的各种模块及配置信息，npm install根据这个配置文件，自动下载所需的运行和开发环境
```
- src：项目源文件夹
- node_modules：项目的依赖类库
- sign：签名模块，当前仅有debug签名，如果内测上线，请添加release文件夹，增加线上签名；签名生成方法请参考文档：编译工具的openssl

3. 手机安装调试器

调试器APK是一个Android应用程序，请从[站点地址下载](https://statres.quickapp.cn/quickapp/quickapp/201803/file/201803200129552999556.apk)

![image](https://doc.quickapp.cn/tutorial/getting-started/hello-world.1.png)

- 扫码安装：配置HTTP服务器地址，下载rpk包，并唤起平台运行rpk包
- 本地安装：选择手机文件系统中的rpk包，并唤起平台运行rpk包
- 在线更新：重新发送HTTP请求，更新rpk包，并唤起平台运行rpk包
- 开始调试：唤起平台运行rpk包，并启动远程调试工具

注意：若无法正常使用调试器，请升级手机系统到最新版本或安装平台预览版

我华为荣耀更新最新版本也是不行，所以直接下载平台流量版

### 手机安装平台预览版
平台预览版APK是一个Android应用程序，请从[站点地址下载](https://statres.quickapp.cn/quickapp/quickapp/201803/file/201803200130021102030.apk)

安装完成后调试应用就能使用了

4. 在平台上运行rpk包
- 编译打包后会在dist文件夹生成rpk包
- 导入到Android设备
- 在快应用调试器选择本地安装，选择rpk包进行安装即可，这样就完成第一个快应用

![image](https://doc.quickapp.cn/tutorial/getting-started/hello-world.2.png)

5.遇到的问题，慢慢研究
- 快应用调试不能直接使用
- 不能通过扫描安装rpk包



