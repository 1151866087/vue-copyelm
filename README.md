## 1.vm的配置

- Indedicated config files
- 配置post.config.js
- 安装npm
- 配置index.html

#### 操作流程操作流程

##### 1. 1使用`vuecli3`创建项目

```
vue create vue-project
```

- 此项目勾选了 vue-router, vuex, babel

```
需要注意的是: 询问配置 PostCSS 时需要选择的是 `In dedicated config files` 在专用配置文件中
? Where do you prefer placing config for Babel, PostCSS, ESLint, etc.? (Use arrow keys)
> In dedicated config files
  In package.json
```

##### 1.2配置`postcss.config.js`

~~~
module.exports = {
  "plugins": {
    "postcss-import": {},
    "postcss-url": {},
    "postcss-aspect-ratio-mini": {}, 
      "postcss-write-svg": {
        utf8: false
      },
      "postcss-cssnext": {},
      "postcss-px-to-viewport": {
        viewportWidth: 750, // 视窗的宽度，对应的是我们设计稿的宽度，一般是750 
        viewportHeight: 1334, // 视窗的高度，根据750设备的宽度来指定，一般指定1334，也可以不配置 
        unitPrecision: 3, // 指定`px`转换为视窗单位值的小数位数（很多时候无法整除） 
        viewportUnit: 'vw', // 指定需要转换成的视窗单位，建议使用vw 
        selectorBlackList: ['.ignore', '.hairlines'], // 指定不转换为视窗单位的类，可以自定义，可以无限添加,建议定义一至两个通用的类名 
        minPixelValue: 1, // 小于或等于`1px`不转换为视窗单位，你也可以设置为你想要的值 
        mediaQuery: false // 允许在媒体查询中转换`px` 
      }, 
      "postcss-viewport-units":{},
      "cssnano": {
        preset: "advanced",
        autoprefixer: false,
        "postcss-zindex": false
      },
  }
}
~~~

##### 1.3安装npm

~~~
npm i cssnano postcss-aspect-ratio-mini postcss-cssnext postcss-px-to-viewport postcss-viewport-units postcss-write-svg -S
npm i cssnano-preset-advanced -D
npm i postcss-import postcss-url autoprefixer -D
~~~

##### 1.4配置index.html

~~~
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width,initial-scale=1.0">
    <link rel="icon" href="<%= BASE_URL %>favicon.ico">
    <title>vuecli3vw</title>
  </head>
  <body>
    <noscript>
      <strong>We're sorry but vuecli3vw doesn't work properly without JavaScript enabled. Please enable it to continue.</strong>
    </noscript>
    <div id="app"></div>
    <!-- built files will be auto injected -->


    <script src="//g.alicdn.com/fdilab/lib3rd/viewport-units-buggyfill/0.6.2/??viewport-units-buggyfill.hacks.min.js,viewport-units-buggyfill.min.js"></script>
    <script>
      window.onload = function () {
        window.viewportUnitsBuggyfill.init({
          hacks: window.viewportUnitsBuggyfillHacks
        });
      }
    </script>
  </body>
</html>
~~~

##### 1.5直接使用就可以了

## 2.配置border.css,reset.css

在main.js中引入

~~~
import './assets/style/reset.css'
import './assets/style/border.css'
~~~

[文件地址](https://gitee.com/chengbenchao/vue-resource) 

## 3.配置fastclick

~~~
//解决移动端300毫秒延迟问题
npm i fastclick --save
//之后再main.js配置
import fastClick from "fastclick"
fastClick.attach(document.body)
~~~

## 4.配置iconfont

##### 4.1下载iconfont

~~~
只需要
iconfont.css
iconfont.eot
iconfont.svg
iconfont.ttf
iconfont.woff
这五个文件,放置在assets-style文件夹下。
~~~

##### 4.2在`main.js`引入

~~~
//在此配置之后,全局都可以使用
import './assets/style/iconfont/iconfont.css'
~~~

##### 4.3在页面在使用

~~~
<span class="iconfont back">&#xe602;</span>
~~~



