# BUI Fast 使用说明

| **作者**   | **描述**            | **修改日期**            |
|:------------- |:-------------------|-------------------:|
| 王伟深       | 更新API 1.0.6    | 2016-07-25    |
| 王伟深       | 更新API 1.0.7    | 2016-08-30    |
| 王伟深       | 更新API 1.2    | 2016-11-04    |

## 目录
-   简介
-   安装说明
-   使用示例
-   BUI HTML结构缩写一览
    * 页面结构
    * 布局结构
    * 控件结构
    * 表单元素结构

-   BUI JS方法及控件缩写请查看 [API文档](http://eid.bingosoft.net:82/bui/demo/api/) 

---
### 简介

BUI Fast 是BUI提供的Sublime扩展插件，在Sublime中集成BUI控件及方法的代码提示，为快速开发助力. 里面封装了控件的常用参数及常用方法的语法补全, 但API的更新不一定是最新的,请一定从官网下载替换, 参数的使用说明,请查看 [API文档](http://eid.bingosoft.net:82/bui/demo/api/) (右键新开窗口).

---
### 安装说明

#### 手动安装
**Windows**: 复制BUI Fast目录到 sublime text的安装目录\Data\Packages\
**Mac**: 打开顶部 Sublime Text 菜单 --> Preferences --> Browse Packages ,复制BUI Fast目录进去就好

#### 自动安装

由于目前这个插件还没正式提交到官网,所以暂时不支持用命令行下载安装的方式. 


---
### 使用示例

html触发结构代码片段的指令格式为: 'ui-控件名'，之后点击<kbd>Tab</kbd>键即可进行补全
JS触发代码片段的指令格式为： 'bui-控件名'，之后点击<kbd>Tab</kbd>键即可进行补全

**注意:** 生成代码后, 按<kbd>Tab</kbd>会定位在常用的编辑区域, 如果要写另外的控件代码, 要先按 <kbd>Esc</kbd> 再重复之前操作.

#### HTML 快速生成BUI控件结构
(在body里面书写)
__ui-list__ <kbd>Tab</kbd> ( 生成列表结构 )

```html
<ul class="bui-list">
    <li class="bui-btn">文本</li>
</ul>
```

**注意**:如果忘记控件的名字, 输入 &lt;ui- 会有提醒相关的控件 ( 生成的结构记得删掉第一个 &lt; ).

#### JS 快速生成BUI常用方法
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

#### JS 快速生成BUI控件
(在script里面书写)

__bui-list__ <kbd>Tab</kbd>  ( 生成list控件的初始化 )

```js
var uiList = bui.list({
    id: "#${1:uiList}",
    url: "${2:userlist.json}",
    data: {},
    template: template,
    onLoad: function (scroll) {
        // 自定义渲染
    },
    callback: function (e) {
        // 点击单行回调 console.log($(this).text())
    },
    height: 0,
    page:1,
    pageSize:10,
    field: {
        page: "page",        // 分页字段
        size: "pageSize",    // 页数字段
        data: "data"         // 数据
    }
});

//生成列表的模板
function template (data) {

    var html = "";

        $(data).each(function(index, el) {

            html += '<li class="bui-btn"><i class="icon-facefill"></i>'+el.name+'</li>';
        });

    return html;
};
```


---
### BUI HTML结构缩写一览

**页面结构**

| **缩写代码**   | **描述**            |
|:------------- |:-------------------|
| ui-html       | BUI HTML标准结构    |
| ui-page       | BUI 页面标准结构    |
| ui-bar        | 生成横条结构        |
| ui-bar-side   | 生成横条左对齐结构   |
| ui-btn             | 按钮                         |
| ui-btn-icon        | 图标按钮                         |
| ui-btn-round        | 圆角按钮                         |
| ui-btn-badges        | 按钮数字提醒                         |
| ui-btn-disabled        | 按钮禁止点击                         |
| ui-panel      | panel结构          |
| ui-table      | 表格结构            |
| ui-form       | 表单结构            |
| ui-form-edit  | 表单填写结构        |
| ui-form-submit| 提交按钮结构        |
| ui-nav | 导航菜单        |
| ui-nav-icon | 导航菜单带图标        |
| ui-list  | 列表结构       |
| ui-list-arrow  | 列表带箭头结构       |
| ui-list-checkbox  | 列表多选结构       |
| ui-list-radio  | 列表单选结构       |
| ui-list-group  | 列表分组结构       |
| ui-list-icon  | 列表带图标结构       |
| ui-list-thumbnail  | 列表多行带缩略图结构       |



**布局结构**

| **缩写代码**   | **描述**            |
|:------------- |:-------------------|
| ui-box        | 弹性布局结构       |
| ui-box-space  | 弹性布局留白结构    |
| ui-box-center  | 块元素水平垂直居中结构    |
| ui-box-align-top  | 块元素顶部对齐结构    |
| ui-box-align-bottom  | 块元素底部对齐结构    |
| ui-box-align-left  | 块元素左对齐结构    |
| ui-box-align-right  | 块元素右对齐结构    |
| ui-box-align-center  | 块元素水平居中结构    |
| ui-box-align-middle  | 块元素垂直居中结构    |
| ui-box-align-justify  | 块元素两端分布结构    |
| ui-box-align-stretch  | 块元素上下拉伸结构    |
| ui-fluid      | 百分比布局结构      |
| ui-fluid-space| 百分比留白布局结构    |
| ui-fluid-2    | 2列布局结构        |
| ui-fluid-3    | 3列布局结构        |
| ui-fluid-4    | 4列布局结构        |


**控件结构**

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
| ui-progress  | 进度条结构       |
| ui-rating  | 星级评分结构       |
| ui-scroll  | 滚动控件结构       |
| ui-sidebar  | 滚动控件结构       |
| ui-slide  | 滑动控件结构       |
| ui-slide-tab  | 滑动Tab控件结构       |


**表单元素结构**

| **缩写代码**        | **描述**                      |
|:-------------      |:-------------------          |
| ui-radio           | 单选框                        |
| ui-checkbox        | 多选框                        |
| ui-checkbox-custom | 多选框自定义结构,便于修改样式    |
| ui-choose | 单选多选的不同样式                       |
| ui-input | 输入框                                    |  
| ui-input-custom | 输入框弹性布局结构                   |
| ui-switch | 开关切换                                  |
| ui-range | 拖动条                                    |

### BUI JS方法及控件缩写请查看 [API文档](http://eid.bingosoft.net:82/bui/demo/api/) 
