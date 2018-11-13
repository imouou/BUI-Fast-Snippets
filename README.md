# BUI Fast 使用说明

|**描述**            | **修改日期**            |
|:-------------------|-------------------:|
| 更新API 1.0.6    | 2016-07-25    |
| 更新API 1.0.7    | 2016-08-30    |
| 更新API 1.2    | 2016-11-04    |
| 更新API 1.3.1 新增事件,更新参数,新增完整示例缩写   | 2017-03-20    | 
| 取消大部分自动定位到预编辑的内容   | 2017-03-30    |
| 修改 bui-slide-demo-pic,bui-slide-demo-tab 为bui-slide-pic-demo,bui-slide-tab-demo   | 2017-05-27    |
| 修改 bui-searchbar-demo ui-list  | 2017-06-08    |
| 新增 ui-router bui-router bui-loader 等相关内容  | 2017-12-20    |
| 新增 ATOM, APICloud 插件支持  | 2018-03-14   |
| 新增 router preload 方法  | 2018-03-27   |
| 新增 webstorm插件  | 2018-04-19   |
| 新增 tab 的几种不同位置, bui-slide-tab-head-demo,bui-slide-tab-foot-demo,bui-slide-tab-side-demo,bui-slide-tab-scroll-demo,  | 2018-05-30   |
| 去除生成控件方法,比方之前有 bui-accordion-show 现在只有 bui-accordion ,只保留最简单的初始化,其它查API   | 2018-06-04   |
| 优化简化,按1.5.0修改   | 2018-09-28   |
| 新增 ui-icon等相关布局, vscode,atom,sublimetext     | 2018-11-12     |

## 目录
[TOC]

---
## 简介

BUI Fast 是BUI提供的快速书写代码提示插件，在Sublime,Atom,VSCode,APICloud Studio2 ,Webstorm中集成BUI控件及方法的代码提示，为快速开发助力. 里面封装了控件的常用参数及常用方法的语法补全, 版本对应 BUI的版本.
> 1.3.1版本新增 控件名加"-demo" 快速生成控件初始化及结构,只要把结构复制到body对应的位置就行.

---
## 安装

### 1. bui-fast 插件

> 下载解压以后,找到对应的编辑器插件

<a href="https://github.com/imouou/BUI-Fast-Snippets/releases/latest" target="_blank">点击下载 BUI Fast 插件</a>

### 在VScode安装 `推荐`

方法1:
在应用市场输入 `bui-fast` , 安装即可. 


### 在Sublimetext安装

*Sublimetext 安装 BUI-Fast*

- *Windows*: 打开顶部 Sublime Text 菜单 --> Preferences --> Browse Packages , 
复制`BUI-Fast-Snippet-SublimeText`目录进去就好.


- *Mac*: 打开顶部 Sublime Text 菜单 --> Preferences --> Browse Packages ,复制`BUI-Fast-Snippet-SublimeText`目录进去就好

### 在Atom,APICloud安装

*Atom ,APICloud Studio2 安装 BUI-Fast*

使用快捷键 mac: `command + shift + p` , windows: `ctrl + shift + p`;

- 输入`open your snippets`, 回车;
打开下载的 `bui-fast-snippet-atom/snippets.cson` 文件, 复制内容到 `snippets.cson` 文件里面, 保存即可.

### 在Webstorm安装

*Webstorm 安装 BUI-Fast*

方法1: 

- 打开下载的 `bui-fast-snippet-webstorm` windows 目录, 复制 settings.jar 到桌面.

- 打开顶部菜单 `File` -> `Import Settings`, 找到刚刚的 settings.jar 

- 重新启动webstorm 就可以了

方法2:

> mac 的安装有可能会出现 import Settings 导入成功,但是无法使用的情况, 是因为webstorm的导入把templates导入在根目录了`WebStorm2017.3/templates`, 正确的目录应该是 `WebStorm2017.3/settingsRepository/repository/templates`. 

复制 `bui-fast-snippet-webstorm/templates` 目录,替换 `资源库/Preferences/WebStorm2017.3/settingsRepository/repository/templates`


---
## 简单使用示例

?> 需要保存文件后缀为.html以后才能生效

*ui-html 演示:*

![ui-html](http://www.easybui.com/docs/images/ui-html.gif)

*ui-page 演示:*

![ui-page](http://www.easybui.com/docs/images/ui-page.gif)

*bui-slide-demo 演示:*

![bui-slide-demo](http://www.easybui.com/docs/images/bui-slide-demo.gif)


html触发结构代码片段的指令格式为: 'ui-控件名'，之后点击<kbd>Tab</kbd>键即可进行补全
JS触发代码片段的指令格式为： 'bui-控件名'，之后点击<kbd>Tab</kbd>键即可进行补全

**注意:** 生成代码后, 按<kbd>Tab</kbd>会定位在常用的编辑区域, 如果要写另外的控件代码, 要先按 <kbd>Esc</kbd> 再重复之前操作.

#### HTML 快速生成BUI控件结构
(在body里面书写)
__ui-accordion__ <kbd>Tab</kbd> ( 生成折叠菜单结构 )

```html
<dl id="uiAccordion" class="bui-accordion">
  <dt class="bui-btn bui-box">
      <div class="span1"><!--折叠菜单--></div>
      <i class="icon-accordion"></i>
  </dt>
  <dd>
      <!--折叠菜单内容-->
  </dd>
</dl>
```

<strong class="hint">**注意**</strong>:如果忘记控件的名字, 输入<strong style="color:red;"> &lt;ui-</strong> 会有提醒相关的控件 ( <strong style="color:red;">生成的结构记得删掉第一个 &lt; </strong> ).


### JS 快速生成BUI控件初始化
(在script里面书写)

__bui-accordion__ <kbd>Tab</kbd>  

```js
var uiAccordion = bui.accordion({
  id:"#uiAccordion"
});

```


### JS 快速生成完整demo  ( 推荐, 1.3.0 新增 )
(在script里面书写)

__bui-list-demo__ <kbd>Tab</kbd>  ( 生成list控件的初始化跟html结构 )

需要把html结构剪切到对应的位置去. 更多demo 请查看底部的控件列表

```
// 列表控件 js 初始化: 

var uiList = bui.list({
  id: "#uiList",
  url: "",
  data: {},             // 数据请求带过去的参数,分页在field配置
  template: listTemplate,
  field: {
      page: "page",     // 分页参数名
      size: "pageSize", // 分页大小参数名
      data: ""          // 数据字段名
  }
});
// 列表模板
function listTemplate (data) {
  var html = "";
  $.each(data,function(index, el) {
      html += '<li class="bui-btn" href="index.html"><i class="icon-facefill"></i>'+el.name+'</li>';
  });

  return html;
}

// 列表控件 html 对应的结构: 

<div id="uiList" class="bui-scroll">
  <div class="bui-scroll-head"></div>
  <div class="bui-scroll-main">
      <ul class="bui-list">
      </ul>
  </div>
  <div class="bui-scroll-foot"></div>
</div>

```

### JS 快速生成BUI常用方法
(在script里面书写)

__bui-ajax__ <kbd>Tab</kbd> ( 生成请求的方法 )

```js
bui.ajax({
    url: "http://",
    data: {},//接口请求的参数

    // 可选参数
    method: "GET",
    timeout: 20000
}).done(function(result){
    
}).fail(function(result){
    
});
```

---


## BUI JS方法及控件缩写

JS触发代码片段的指令格式为： 'bui-控件名'，之后点击<kbd>Tab</kbd>键即可进行补全

#### 控件简单初始化

控件名: bui.accordion 
我们只需要输入 __bui-accordion-demo__ <kbd>Tab</kbd> 就会生成完整的示例

### 控件完整demo缩写一览 (推荐 1.3.0新增)

| **缩写代码**   | **描述**            |
|:------------- |:-------------------|
| bui-accordion-demo  | 折叠菜单完整示例       |
| bui-actionsheet-demo  | 上拉菜单完整示例       |
| bui-dialog-demo  | 弹出框完整示例       |
| bui-dropdown-demo  | 下拉菜单完整示例       |
| bui-list-demo  | 列表侧滑完整示例       |
| bui-listview-demo  | 列表侧滑完整示例       |
| bui-listview-demo-custom  | 列表侧滑静态完整示例       |
| bui-pullrefresh-demo  | 下拉刷新完整示例       |
| bui-scroll-demo  | 滚动控件完整示例       |
| bui-number-demo  | 数字条完整示例       |
| bui-pickerdate-demo  | 日期完整示例       |
| bui-rating-demo  | 星级评分完整示例       |
| bui-scroll-demo  | 滚动控件完整示例       |
| bui-sidebar-demo  | 滚动控件完整示例       |
| bui-slide-demo  | 焦点图滑动完整示例       |
| bui-tab-demo  | Tab控件-示例  |
| bui-tab-demo-footer  | Tab控件菜单在底部滚动-示例  |
| bui-swipe-demo  | 抽屉菜单完整示例       |
| bui-levelselect-demo  | 级联菜单完整示例       |
| bui-input-demo  | 输入框完整示例       |
| bui-searchbar-demo  | 搜索完整示例       |
| bui-select-demo  | 选择列表完整示例       |
| bui-stepbar-demo  | 步骤条完整示例       |
| bui-upload-demo  | 上传完整示例       |

控件名: bui.accordion 
我们只需要输入 __bui-accordion__ <kbd>Tab</kbd> 就会生成最简单的初始化脚本


| **缩写代码**   | **描述**            |
|:------------- |:-------------------|
| bui-accordion  | 折叠菜单初始化       |
| bui-actionsheet  | 上拉菜单初始化       |
| bui-dialog  | 弹出框初始化       |
| bui-dropdown  | 下拉菜单初始化       |
| bui-list  | 列表初始化       |
| bui-listview  | 列表侧滑初始化       |
| bui-pullrefresh  | 下拉刷新初始化       |
| bui-scroll  | 滚动加载初始化       |
| bui-number  | 数字条初始化       |
| bui-pickerdate  | 日期初始化       |
| bui-rating  | 星级评分初始化       |
| bui-searchbar  | 搜索控件初始化       |
| bui-sidebar  | 滚动控件初始化       |
| bui-slide  | 滑动控件初始化       |
| bui-tab  | 滑动Tab控件初始化  |
| bui-swipe  | 抽屉菜单初始化       |
| bui-levelselect  | 级联菜单初始化       |
| bui-input  | 输入框初始化       |
| bui-searchbar  | 搜索初始化       |
| bui-select  | 选择列表初始化       |
| bui-stepbar  | 步骤条初始化       |
| bui-upload  | 上传初始化       |
| bui-router  <span style="color:red">新</span> | BUI 单页初始化 |
| router-load  <span style="color:red">新</span> | 单页跳转 |
| router-refresh  <span style="color:red">新</span> | 单页刷新 |
| router-replace  <span style="color:red">新</span> | 单页替换 |
| router-back  <span style="color:red">新</span> | 单页后退 |
| router-getPageParams  <span style="color:red">新</span> | 获取页面参数 |
| router-loadPart  <span style="color:red">新</span> | 局部加载 |
| loader-define  <span style="color:red">新</span> | 模块定义 |
| loader-require  <span style="color:red">新</span> | 模块加载 |
| loader-import  <span style="color:red">新</span> | 脚本及样式资源动态引入 |
| loader-map  <span style="color:red">新</span> | 单个模块配置 |
| loader-mapall  <span style="color:red">新</span> | 多个模块配置 |


## BUI HTML结构缩写一览

html触发结构代码片段的指令格式为: 'ui-控件名'，之后点击<kbd>Tab</kbd>键即可进行补全



### 控件结构缩写

| **缩写代码**   | **描述**            |
|:------------- |:-------------------|
| ui-accordion  | 折叠菜单结构       |
| ui-actionsheet  | 上拉菜单结构       |
| ui-dialog  | 弹出框结构       |
| ui-dropdown  | 下拉菜单结构       |
| ui-listview  | 列表侧滑结构       |
| ui-listview-custom  | 列表侧滑静态结构       |
| ui-number  | 数字条结构       |
| ui-pickerdate  | 日期结构       |
| ui-rating  | 星级评分结构       |
| ui-list  | 列表滚动控件结构       |
| ui-scroll  | 滚动控件结构       |
| ui-sidebar  | 滚动控件结构       |
| ui-slide  | 滑动控件结构       |
| ui-slide-tab  | 滑动Tab控件结构  |
| ui-swipe  | 抽屉菜单结构       |
| ui-searchbar  | 搜索结构       |
| ui-range  | 滑动条结构       |
| ui-switch  | 切换按钮结构       |
| ui-select  | 选择列表结构       |
| ui-stepbar  | 步骤条结构       |
| ui-btn             | 按钮                         |
| ui-levelselect  <span style="color:red">新</span>| 级联控件结构       |
| ui-tab  <span style="color:red">新</span>| 选项卡结构       |
| ui-upload  <span style="color:red">新</span>| 上传结构       |
| ui-input | 输入框                                    |  

### 页面结构缩写

| **缩写代码**   | **描述**            |
|:------------- |:-------------------|
| ui-router  <span style="color:red">新</span>     | BUI 单页标准结构    |
| ui-html       | BUI HTML标准结构    |
| ui-page       | BUI 页面标准结构    |
| ui-header        | 生成header结构        |
| ui-header-side   | 生成header左对齐结构   |
| ui-panel      | panel结构          |
| ui-table      | 表格结构            |
| ui-form       | 表单结构            |
| ui-form-edit  | 表单填写结构        |
| ui-form-submit| 表单底部结构        |
| ui-nav | 导航菜单        |
| ui-nav-icon | 导航菜单带图标        |
| ui-list-arrow  | 箭头列表结构       |
| ui-list-checkbox  | 多选列表结构       |
| ui-list-radio  | 单选列表结构       |
| ui-list-group  | 分组列表结构       |
| ui-list-icon  | 图标列表结构       |
| ui-list-photo  | 图片列表结构       |
| ui-list-thumbnail  | 列表多行带缩略图结构       |


### 布局结构缩写

| **缩写代码**   | **描述**            |
|:------------- |:-------------------|
| ui-box        | 弹性布局结构       |
| ui-box-space  | 弹性布局留白结构    |
| ui-box-center  | 块元素水平垂直居中结构    |
| ui-fluid      | 百分比布局结构      |
| ui-fluid-space| 百分比留白布局结构    |
| ui-fluid-5    | 5列布局结构        |


### 表单元素结构缩写

| **缩写代码**        | **描述**                      |
|:-------------      |:-------------------          |
| ui-radio           | 单选框                        |
| ui-checkbox        | 多选框                        |
| ui-checkbox-custom | 多选框自定义结构,便于修改样式    |
| ui-choose | 单选多选的不同样式                       |
| ui-switch | 开关切换                                  |
| ui-range | 拖动条                                    |
| ui-progress  | 进度条结构       |
| ui-check  <span style="color:red">新</span>| 选择按钮结构       |
