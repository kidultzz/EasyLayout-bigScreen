# :house: EasyLayout-bigScreen
## :memo:介绍
 >    通过拖拽布局的方式可视化搭建大屏页面。提供了画布、容器和标题三种基本的大屏布局组件，通过对不同组件的配置组合，可实现基本的大屏要素搭建模板。通过工程文件模板下载，为后续开发人员提供了基本的项目开发环境。
 >![main-interface.png](https://p5-tt.byteimg.com/origin/pgc-image/61fa2aca5a27444a88c53fe74fe12d44.png)

## :hammer_and_wrench:技术栈
* **React** 前端框架
* **redux Toolkit** 状态管理工具
* **antd** react组件库
* **axios** 前端请求库
* **react-dnd** 基于react的拖拽工具
* **immutability-helper** 复杂数据副本处理方案
* **webpack5** 模块打包器

## :symbols:配置模板
>    用户的每一步配置操作都会被记录下来并保存为一个json格式的数据模板，例如容器组件的定位、大小、背景配置、颜色配置等等。以数据格式的尽量精简和易读为目的，配置模板的设计方案大体分为容器配置模板和画布（页面）配置两大类，由于容器可以创建多个，因此容器配置模板设计为一个数组，数组元素为所创建的容器组件配置对象;画布（页面）配置为一个对象,保存了所有画布上的配置信息。设计结构如下所示：
```js
{
  //容器配置模板
  "componentTpl": [{...}],
  //画布页面配置模板
  "pageConfig": {...}
}
```

    我们把标题组件的配置信息分别放进了容器配置模板和画布配置模板的结构中，为了区分其输入容器组件的标题还是画布的标题，设计一个“link”字段来标记该标题组件的所属对象。如果标题属于某个容器内部，“link”字段存储了该标题组件所属容器的编号;如果标题属于画布，则“link”字段为空。
每个容器组件的配置包含了基本配置信息、样式信息和标题信息。大致结构如下：

```js
{
  "config": {
    "type": "container",
    "No": 0,
    "top": "2.5%",
    "left": "6.25%",
    "title": "容器1",
    "bgImg": "containerImg1",
    ...
  },
  "style": {
    "top": "2.5%",
    "left": "6.25%",
    "width": "12.5%",
    "height": "20%",
    "backgroundColor": "rgba(160,74,74,0)",
    ...
  },
  "title": [{
    "id": "container0Title0",
    "title": "标题1",
    "style": {
    ...
    }
  }]
}
```
## :card_index_dividers:工程文件下载
>   工程文件按照规范的react目录结构，包含了一些基础的webpack配置和工具库，把保存的json配置数据进行解析和渲染，
>   
### Install
1. DownLaod
```sh
git clone https://github.com/kidultzz/EasyLayout-bigScreen.git
```
2. Install
```bash
npm install
```
or
```bash
cnpm install
```
### Usage

本地启动
```sh
npm run dev
```
打包
```sh
npm run prod
```
