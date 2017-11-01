# 静态文件的部署

由于早期引用的部分国外资源文件访问速度较慢，需要部署在本地，并修改为本地引用地址：

#### 1，对部分引用国外CDN静态资源改为本地部署或引用国内CDN地址

本地部署需要修改所有OVP和ICC的引用地址，参见附件localCDN文件包

下载地址：

```
链接: https://pan.baidu.com/s/1kVQRfpX 密码: rgnz
```

#### 2，修改font-awesome引用

A，部署本地文件：推荐

```
包含 css 目录下 /font-awesome.min.css 以及 fonts 目录下 /fontawesome-webfont.woff2
```

B，国内CDN地址：

```
<link href="https://cdn.bootcss.com/font-awesome/4.5.0/css/font-awesome.min.css" rel="stylesheet">
```

#### 3，引用 ionicons.min.css

A，部署本地文件：推荐

```
包含 ionicons 目录下的 /ionicons.min.css 文件
```

B，国内CDN地址：

```
<link href="https://cdn.bootcss.com/ionicons/2.0.1/css/ionicons.min.css" rel="stylesheet">
```

4，引用Google统计文件无法避免

```
例如以下域名地址不可避免，但不干扰访问功能
https://www.googletagmanager.com
```



