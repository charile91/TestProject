<template>
  <div id="app">
    <!-- 子组件Tfrom.vue注册的FromData -->
    <tfrom v-on:FromData="translateText"></tfrom>
    <toutput v-text="viewText"></toutput>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import Tform from "./components/Tform";
import Toutput from "./components/Toutput";
export default {
  name: "App",
  data: function() {
    return {
      // 定义viewText接收翻译后的文字
      viewText: ""
    };
  },
  components: {
    tfrom: Tform,
    toutput: Toutput
  },
  methods: {
    // text用来接收子组件Tfrom.vue传的值
    translateText: function(text, lang) {
      // alert(text);
      // 请求翻译API
      this.$http
        .get(
          "https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180726T093029Z.39171bcc03d8d26e.be904ae79769804f06f9c73e099515b42de3ac27&lang=" +
            lang +"&text=" +text
        )
        .then(response => {
          // console.log(response.body.text[0]);
          this.viewText = response.body.text[0];
        });
    }
  }
};
</script>

<style>
</style>
