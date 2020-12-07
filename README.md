# vue-luck-draw

> 基于手机端的大转盘抽奖

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
```
![输入图片说明](https://gitee.com/uploads/images/2018/0326/154139_7a6a6549_1622270.gif "GIF.gif")

> 引用
```
以组件的方式引入。
抽中指定商品通过后台返回,在组件里面的OnRotate()
从服务器获取用户真实的获奖信息（对应的获奖序号）
<template>
  <div id="app">
    <v-luck-draw :rewardNames="rewardNames" @OnClick="OnLuck" ref="luckDraw"></v-luck-draw>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      rewardNames: ["mp3", "iphone8", "谢谢参与", "iphoneX", "ipad mini4"]
    };
  },
  mounted() {},
  methods: {
    //点击旋转按钮后,子组件返回的抽中的奖品名称
    OnLuck(data) {
      alert(data);
    }
  },
  components: {
    //按自己的需求，也可以不用异步加载
    //异步加载组件
    "v-luck-draw": () => import("./components/luck-draw/luck-draw.vue")
  }
};
</script>

<style>

</style>
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
