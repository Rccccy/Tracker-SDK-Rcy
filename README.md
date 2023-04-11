### 编译

rollup打包干净适合SDK和一些框架,webpack适合项目
2023-04-10 edit
最好按照下面的版本, rollup-plugin-dts的高版本容易出问题
```json
    "rollup": "^2.77.0",
    "rollup-plugin-dts": "^4.2.2",
    "rollup-plugin-typescript2": "^0.32.1",
```

### 核心(core)
>PV: 页面访问量,即page-view,用户每次对网站的访问均被记录
主要监听了history和hash
1. history 无法通过 popState(可以监听左右两个按钮的历史记录); pushState和replaceState的跳转无法进行监听;只能重写其函数 在utils/pv
2. hash 使用hashChange 监听


> UV: 独立访问,即Unique Visitor,访问您网站的一台电脑客户端为一个访客
用户唯一标识,可以在登录后通过接口返回的id 进行设置值 提供了setUserId,也可以使用canvas指纹追踪技术

**navigator.sendBeacon**
为什么要使用navigator.sendBeacon 来上报?
答: 这个上报的机制 跟 XMLHttpRequest 对比  navigator.sendBeacon 即使页面关闭了 也会完成请求 而XMLHttpRequest 不一定

navigation.sendBeacon 的类型是ping

3. DOM主要是给需要监听的元素添加一个属性 用来区分是否需要监听 target-key

4. js报错上报 error 事件  promise报错 unhandledrejection