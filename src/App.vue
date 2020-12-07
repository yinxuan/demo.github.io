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
    OnLuck(data) {
      alert(data);
    }
  },
  components: {
    //异步加载组件
    "v-luck-draw": () => import("./components/luck-draw/luck-draw.vue")
  }
};
</script>

<style>

</style>
