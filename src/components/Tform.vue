<template>

<div class="row" id="tfrom">
  <div class="col-md-6 col-md-offset-3">
    <h1>在线翻译</h1>
   <form class="well form-inline" v-on:submit="FromSubmit">
<input class="form-control" v-model="textToTranslate" type="text" placeholder="请输入要翻译的内容">
<select class="form-control" v-model="lang">
  <option value="en">English</option>
  <option value="ru">Russian</option>
  <option value="ko">Korean</option>
  <option value="ja">Janpenese</option>
</select>
<input type="submit" value="翻译" class="btn btn-info">
   </form>
  
  </div>
  </div>
</template>

<script>
export default {
  name: "t-form",
  data() {
    return {
      textToTranslate: "",
      // 定义语言类型用
      lang: ""
    };
  },
  created: function() {
    this.lang = "en";
  },
  methods: {
    FromSubmit: function(e) {
      // alert(this.textToTranslate);
      // 注册FromData事件把this.textToTranslate传给父组件App.vue
      this.$emit("FromData", this.textToTranslate, this.lang);
      e.preventDefault();
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#tfrom {
  text-align: center;
}
</style>
