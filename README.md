:running:vueBlog:running:
============

## 目录

* [安装git](#安装git)
* [安装node](#安装node)
* [安装淘宝镜像cnpm](#安装淘宝镜像cnpm)
* [本地运行](#本地运行)
* [打包上传运行](#打包上传运行)

## Demo

> [Moonlight的个人博客](https://moonlightg.github.io/mb)

## 使用方法

#### 下载项目到本地
```
git clone https://github.com/Moonlightg/vueBlog.git
```
#### 本地运行

> 1.安装依赖

```
npm install
```
> 2.在本地开启服务，然后就可以通过 http://localhost:8084 访问了

```
npm run dev
```
> 3.[创建 OAuth Application](https://github.com/settings/applications/new)

3.1 

![image](https://user-images.githubusercontent.com/14285531/30852074-2d843fa0-a2dd-11e7-8fd2-7e701e171428.png)

3.2

![image](https://user-images.githubusercontent.com/14285531/30852109-49c09146-a2dd-11e7-9b9f-b2855a247fa1.png)

3.3

![image](https://user-images.githubusercontent.com/14285531/30852131-58457308-a2dd-11e7-90cd-f5b756c684d4.png)

3.4

![image](https://user-images.githubusercontent.com/14285531/30852226-a2559360-a2dd-11e7-9e88-4c786ca44f1b.png)

3.5

![image](https://user-images.githubusercontent.com/14285531/30852245-b5330cce-a2dd-11e7-9e09-9911b1ccfb47.png)



> 4.个人配置 - 修改「BGAIssueBlog/src/store/account.js」文件中的「state」属性

```JavaScript
const state = {
  accessToken: localStorage.getItem(LS_KEY_ACCESS_TOKEN),  // 这个不要修改，这个不要修改，这个不要修改。当前登录用户的 GitHub AccessToken
  auth: {
    proxy: 'https://cors-anywhere.herokuapp.com/https://github.com/login/oauth/access_token', // 这个不要修改，这个不要修改，这个不要修改。
    clientID: '8fe09ec96875938b908d',   // 改成你在 https://github.com/settings/applications/new 新建的 OAuth application 的 Client ID
    clientSecret: '46df51ccde6f3499c3b90861bba660fb1bcf15e4'  // 改成你在 https://github.com/settings/applications/new 新建的 OAuth application 的 Client Secret
  },
  gitHubUser: null,  // 这个不要修改，这个不要修改，这个不要修改。
  gitHubUsername: 'bingoogolapple',  // 修改成你自己的 GitHub 账号
  copyright: '2014 - 2017',  // 修改成你自己的
  recordNumber: '蜀ICP备17023604号',  // 修改成你自己的备案编号，如果没有备案的话就设置为 null
  repo: 'bingoogolapple/bingoogolapple.github.io',  // 记录 Issue 的仓库的全名「用户名/仓库名」
  pageSize: 10,  // 博客列表每页显示多少条博客
  showQQGroup: true,  // 如果要显示你自己的 QQ 群二维码图片的话这里配置成 true 并且替换「BGAIssueBlog-Web/static/img/qq-group.png」为你自己的 QQ 群二维码图片，否则配置成 false 即可
  thirdPartySite: [  // 配置你想在左上角展示的第三方站点信息
    {
      img: 'static/img/github.png',  // 第三方站点图标，存放在「BGAIssueBlog-Web/static/img」目录中
      url: 'https://github.com/bingoogolapple'  // 第三方站点的 url
    },
    {
      img: 'static/img/weibo.png',
      url: 'http://weibo.com/bingoogol'
    },
    {
      img: 'static/img/git.png',
      url: 'https://bingoogolapple.gitbooks.io/bgalearningnotes-git/content'
    }
    // 如果还有其他站点需要显示，继续在这里追加
  ]
}
```
> 5.个人配置 - 修改网站图标

```
修改「BGAIssueBlog/static/img/favicon.ico」文件
```
> 6.个人配置 - 修改网站标题

```
修改「BGAIssueBlog/index.html」文件里「<title>」标签里的内容
```

#### 发布到 GitHub Pages

> 1.打包

```
npm run build
```
> 2.发布

```
拷贝「BGAIssueBlog/docs」目录里的所有文件到「GitHub Pages」的根目录下
并将「GitHub Pages」仓库 PUSH 到 GitHub 上
```

#### 绑定域名到 GitHub Pages

> 1.在「GitHub Pages」根目录下添加文件名为「CNAME」的文件，文件内容就是你的二级域名，例如我的是

```
www.bingoogolapple.cn
```
> 2.登录你的域名控制台添加域名解析

```
「记录类型」选择「CNAME」
「主机记录」填「www」
「记录值」填「GitHub用户名.github.io」，例如我的是「bingoogolapple.github.io」
```

## 关于我

| 新浪微博 | 个人主页 | 邮箱 | BGA系列开源库QQ群
| ------------ | ------------- | ------------ | ------------ |
| <a href="http://weibo.com/bingoogol" target="_blank">bingoogolapple</a> | <a  href="http://www.bingoogolapple.cn" target="_blank">bingoogolapple.cn</a>  | <a href="mailto:bingoogolapple@gmail.com" target="_blank">bingoogolapple@gmail.com</a> | ![BGA_CODE_CLUB](http://7xk9dj.com1.z0.glb.clouddn.com/BGA_CODE_CLUB.png?imageView2/2/w/200) |

## 打赏支持

如果您觉得 BGA 系列开源库帮你节省了大量的开发时间，请扫描下方的二维码随意打赏，要是能打赏个 10.24 :monkey_face:就太:thumbsup:了。您的支持将鼓励我继续创作:octocat:

如果您目前正打算购买通往墙外的梯子，可以使用我的邀请码「YFQ9Q3B」购买 [Lantern](https://github.com/getlantern/forum)，双方都赠送三个月的专业版使用时间:beers:

<p align="center">
  <img src="http://7xk9dj.com1.z0.glb.clouddn.com/bga_pay.png" width="450">
</p>

## License

    Copyright 2016 bingoogolapple

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
