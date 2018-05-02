# learnVue 
> 实战学习Vue的小项目（模仿去哪儿页面）

<br>

[TOC]

## 第1章
### 1-1 课程介绍
##### 学习前提
* .js  
* ES6  
* webpack  
* npm  
<hr><br>

## 第2章
### 2-1 课程学习方法
* 学会阅读官方文档  
### 2-2 使用Vue.jsx实现Hello World 
> bug: `#app` 误写成 `.app`  
### 2-3 使用Vue.js实现TodoList
* `v-for`： 循环迭代  
* `v-on:click`： 事件绑定  
* `v-model`: 数据的双向绑定  
### 2-4 MVVM模式
* MVP模式: Model + View + Presenter   
* MVVM模式: Model(数据) + View(视图) + ViewModel 虚拟DOM  
> 通过jquery实现了TodoList(**MVP模式**)  
### 2-5 前端组件化
* 组件看作是页面上的一个部分，可以把整个页面切分成一个一个的部分  提高维护性  
### 2-6 使用组件化思想修改TodoList
* `Vue.component()`方法注册全局组件  
* `v-bind:`指令  
* 局部组件的创建(一个对象)与注册  
### 2-7 简单的组件间传值
* 子组件与父组件间的传值
* `splice()`函数
* `$emit()`
### 2-8 本章小结
<hr><br>

## 第3章
### 3-1 Vue实例
### 3-2 Vue实例的生命周期钩子
* 生命周期函数就是Vue实例在某一个时间点会自动执行的函数  
### 3-3 Vue模板语法
* `v-text`
* `v-html`
* `v-text=" ... "` & `v-html=" ... "` & `{{ ... }}`里面可以填写js表达式 
### 3-4 计算属性和侦听器
* 计算属性的缓存机制
### 3-5 计算属性的setter和getter
### 3-6 Vue中的样式绑定
<hr><br>

## 第4章  
* ... ...
<hr><br>

## 第5章  
* ... ...
<hr><br>

## 第6章  
### 6-1 项目环境准备
1. 安装 **[Node.js](https://nodejs.org/en/)**  
* `node -v`  
* `npm -v`
<br>
2. 在Git **（码云）** 创建项目 
<br>
3. 下载安装 **[Git](https://git-scm.com/)**  
* `git --version` 
* 使用 **Git Bash**  
* **Git** 在 **windows** 起了一个小型的 **Linux** 系统  
* 如何 [生成ssh公钥](http://git.mydoc.io/?t=154712)  
<br>
4. `git clone ...`
<br>
5. 安装 **[vue-cli](https://cn.vuejs.org/v2/guide/installation.html#%E5%91%BD%E4%BB%A4%E8%A1%8C%E5%B7%A5%E5%85%B7-CLI)** 脚手架
<br>
6. 安装 [**webpack**](https://blog.csdn.net/zhuming3834/article/details/72778147)
* `cd pname(项目目录)`
* `npm install` 安装依赖
* `npm run dev` 本地运行项目
* localhost:8080  
<br>
7. 同步代码
* `git status`
* `git add .` 提交到本地缓冲区  
* `git commit -m '...'` 缓冲区提交到本地仓库  
* `git push`  提交到线上
### 6-2 项目代码结构介绍
### 6-3 **单文件组件**与Vue中的 **路由**  
### 6-4 **多页面应用** VS **单页面应用**
<hr><br>

## 第7章  
### 7-1 首页 **header** 区域的开发
* ... ...  
### 7-2 iconfont的使用和代码优化
* **iconfont** 的使用
* 代码优化
    *  **stylus** 定义颜色变量
    * `~@import` 引入样式文件
    * 使用 ` @ ` 指向 **src** 目录
    * 在 **bulid** 目录下的 **webpack.base.conf.js** 文件里修改 `alias` ，设置经常要使用的目录的别名  
    * 修改了配置文件后要重启服务器 `npm run start` 
### 7-3 首页轮播图
* 创建 git 分支 **index-swiper**
* 线上分支拉到本地
    * `git pull`  
    * `git checkout index-swiper`  
    * `git status`  
* 使用 **vue-awesome-swiper** 轮播图插件
    * [Github](https://github.com/surmon-china/vue-awesome-swiper)  
    * `npm install vue-awesome-swiper@2.6.7 --save` 
    * `npm run start`
    * 引用 **vue-awesome-swiper** 插件
        ```javascript
        import Vue from 'vue'
        import VueAwesomeSwiper from 'vue-awesome-swiper'

        // require styles
        import 'swiper/dist/css/swiper.css'

        Vue.use(VueAwesomeSwiper, /* { default global options } */)
        ```
    * 新建一个 **Swiper** 组件，使用 **vue-awesome-swiper** 插件
    * 前端优化：[巧用margin/padding的百分比值实现高度自适应（多用于占位，避免闪烁）](https://segmentfault.com/a/1190000004231995)
    * `scoped` 限制只能修改当前组件，使用 `>>>` 样式穿透  
    * 使用 `v-for` 循环遍历图片，`loop: true`
    * 提交代码，合并分支
        * `git add .`
        * `git commit -m 'change'`
        * `git push` 提交 **index-swiper** 分支
        * `git checkout master` ，切换到 **master**  
        * `git merge origin/index-swiper` 把线上的 **index-swiper** 分支合并到本地的 **master** 分支  
        * `git push` 提交本地合并后的 **master** 分支  
### 7-4 图标区域页面布局
* 创建 git 分支 **index-icons**
* 
### 7-5 图标区域逻辑实现
* 使用计算属性 **computed** 对 **iconList** 的数据循环
    ```
    computed: {
      pages () {
        const pages = []
        this.iconList.forEach((item, index) => {
          const page = Math.floor(index / 8)
          if (!pages[page]) {
            pages[page] = []
          }
          pages[page].push(item)
        })
        return pages
      }
    }
    ```
* 使用 **Vue.js devtools** 插件
* **ellipsis()**
    ```
    overflow: hidden
    white-space: nowrap
    text-overflow: ellipsis
    ```