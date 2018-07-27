<template>
  <div class="t-output">
  <h2>{{viewText}}</h2>
  </div>
</template>

<script>
export default {
  name: "t-output",
  props: ["viewText"]
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.t-output {
  text-align: center;
}

</style>
