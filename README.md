# ddl-website
## 一个可以创建多个ddl清单并附带倒计时的网页
v1.0by赵铭宇
### 功能
·自定义事件的截止时间、时间名称与备注<br>
·通过目录页可选择要查看的特定ddl列表<br>
·点击事件可查看备注<br>
·自动按剩余时间排序，剩余时间小于1天的事件会标红<br>
·已截止事件仍会保留，倒计时变为负值<br>
·背景使用必应壁纸api，自然美观。<br>

### 安装
在Release界面下载压缩包，解压至服务器，启动服务即可。建议将index.html配置为主网页

### 配置
ddl站由两种网页构成，分别为目录页、ddl列表页

#### 目录页配置
打开index.html并下滑，你会看到
```html
<div class="container">
    <!--下面这行是目录页面的介绍文本框。使用<br>换行-->
    <p contenteditable="true">赵铭宇设计的ddl列表<br>这里你可以替换成你自己的简介<br>点击某个事项将弹出其对应的具体内容备注<br>君子协定，使用时候请标注我的名字赵铭宇</p>
<!--下面是用来设置按钮、按钮上的文字、以及点击按钮打开哪个网页的。例如下面这行，就回生成一个上面写着我是按钮四个字的按钮，点击后会打开同目录下的ddl1.html网页-->
    <button onclick="redirectToClass('ddl1.html')">我是按钮</button>
    <button onclick="redirectToClass('ddl2.html')">我也是啊</button>
    <button onclick="redirectToClass('ddl3.html')">我也一样</button>
<!--上面的按钮可以通过复制粘贴调整数量-->
</div>
```
请按照代码注释在此区域修改代码。

#### ddl列表页配置

##### ddl列表数量
ddl列表页数量不限，你可以复制粘贴出多个ddl列表，并修改前文 **目录页配置** 中的按钮数量 _（复制粘贴新行或删除某行）_  以及修改圆括号中的文件名。<br>
例如，我新复制粘贴了一个ddl文件，文件名为 ddldemo.html，我想让它在目录页被人看到名为“示例ddl”的按钮，那么我就要在index.html的对应位置加上一行<br>
`<button onclick="redirectToClass('ddldemo.html')">示例ddl</button>`

##### ddl列表配置
打开某个ddl文件，如ddl1.html并下滑，你会看到
```html
<script>
// 定义倒计时事件，模块化，不够用可以自己复制粘贴
var events = [
//title为事件名，deadline定义的是事件，remark为备注内容
//备注可以用 \n 来换行
    { title: '示例事件1', deadline: '2024-12-03 20:59:59', remark: '这里换成备注' },
    { title: '示例事件2', deadline: '2024-05-05 23:59:59', remark: '这里换成备注' },
    { title: '示例事件3', deadline: '2024-05-12 08:30:00', remark: '这里换成备注' },
    { title: '示例事件4', deadline: '2026-05-18 14:00:00', remark: '这里换成备注' },

];
```
请按照代码注释在此区域修改代码。

### 网页展示
![网页展示1](https://github.com/Mr-data20/ddl-website/blob/main/demopicture/picture1.jpg)
![网页展示2](https://github.com/Mr-data20/ddl-website/blob/main/demopicture/picture2.jpg)
![网页展示3](https://github.com/Mr-data20/ddl-website/blob/main/demopicture/picture3.jpg)
