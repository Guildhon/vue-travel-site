# Vue实现去哪儿网

由脚手架vue-cli搭建

技术实现：
Vue+Vue-Router+Vuex+axios
CSS使用了stylus预处理器
使用动画效果实现渐隐渐现

npm run dev      开发调试
npm run build    打包上线

### 一些插件

使用keep-alive提高网页性能，组件会把请求过的数据缓存起在内存中，等下次访问时将加载内存的数据

使用better-scroll实现滑动效果和右侧城市选择效果

使用fastclick处理移动端click事件300毫秒延迟

使用vue-awesome-swiper实现轮播图效果

### 需要注意
有些import比如有@之类的到webpack.config.js里面的resolve查找配置

开发环境下url地址转发可以到config目录下index.js的dev模块进行配置

打包上线时要求打包的代码放到哪个文件夹要到build目录的assetsPublicPath进行配置

export default里面name的作用：
组件模板递归调用自己
便于vue-devtools调试
keepalive的exclude使用

递归组件的使用

### 一些坑

组件拖动以后影响其他组件，在router里使用下面代码
```
scrollBehavior (to, from, savedPostion) {
    return {
      x: 0,
      y: 0
    }
}
```
使页面切换回到顶部

babel-polyfill：有些安卓手机出现 白屏问题，给不支持promise之类的安卓手机增加promise特性

style设置了scoped，需要穿透需要设置
selector >>> selector

城市列表A-Z栏下拉页面会跟着下拉，需要阻止默认事件prevent

使用$refs时，如果:ref是循环出来的，会获取一个列表




