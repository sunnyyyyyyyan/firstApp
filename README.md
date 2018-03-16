# vue_test

> first test vue project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

# run unit tests
npm run unit

# run e2e tests
npm run e2e

# run all tests
npm test
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

＃项目目录结构
  index.html:项目根视图
  .postcssrc.js：postcss配置文件
  static：静态文件目录
  
#模板语法
  Vue组件：
      包含三个部分
          template：试图
          script：逻辑
          style：样式
              scoped：只在当前组件内生效
  Mustache：模板
      表现形式：{{语法}}
      {{hello}}
      {{1 + 1}}
      {{"哈哈"}}
      {{ 0 < 10 ? 'yes' : 'no'}}
      {{ 'attention:只能存在单行语句，并且不能作用在html属性上'}}
   Vue的基本指令：
      v-html：渲染文本
      v-text：渲染文本
      v-bind：绑定  
   条件渲染：
      v-if
      v-else
      v-else-if
      v-show
      问题：v-if 与 v-show有什么区别
            v-if是惰性的，v-show不管初始条件是什么，元素都会被渲染出来
   列表渲染：
      v-for
      每个列表都要添加key
   事件监听：
      v-on:
      methods:
      事件参数
      修饰符
      简写方法：@代替v-on   :代替v-bind
   数组更新检测：
      变异方法：引起试图更新
      替换数组：不会引起视图更新
   显示过滤/排序结果：
      filter 
    
   计算属性和观察者
      computed
      计算属性和Methods区别：
          我们可以将同一函数定义为一个方法而不是一个计算属性。两种方式的最终结果确实是完全相同的。然而，不同的是计算属性是基于它们的依赖进行缓存的。计算属性只有在它的相关依赖发生改变时才会重新求值。这就意味着只要 message 还没有发生改变，多次访问 reversedMessage 计算属性会立即返回之前的计算结果，而不必再次执行函数
   表单输入绑定
      v-model：双向数据绑定
      修饰符：lazy,number,trim
   Class 与 Style 绑定
      绑定 HTML Class
      数组语法
   
   子父级组件交互（通信）
      父 -〉 子：props
            数据传递类型限制（验证）
                      数据类型验证
                      多数据类型验证
                      必选项
                      默认值
                      obj、arr数据类型的默认值
            
      子 -〉 父：emit Event
   
使用npm管理组件版本   
    1.npm 发布组件：
        1.1. npm官网注册账号
        1.2. cmd / git bash 下登陆账号：npm login
              username
              password
              email
        1.3. 打包：npm run build
             发布：npm publish
    2.创建自己的组件
        2.1 初始化项目
        2.2 修改package.json文件
              "private": false
              "main": "dist/vue-counter.min.js"
        2.3 修改 webpack.prod.config.js 文件
                修改out输出目录
                    output: {
                        path: config.build.assetsRoot,
                        publicPath: config.build.assetsPublicPath,
                        filename: 'vue-counter.min.js',
                        library:'VueCounter',    //组件名称
                        library:'umd'
                      },
                删除无用内容
        2.4 修改输出
                 修改main.js 文件，输出自己的组件即可使用            

    
