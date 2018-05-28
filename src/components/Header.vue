<template>
  <div class="headerview">
  <h1>{{msg}}</h1> 
  </div>
</template>
<script>
export default {
  data() {
    return {
      title: "title area"
    };
  },
  //父組件傳參數給子組件
  props: {
    // 自定義屬性
    msg: {
      type: String,
      default: "Hello"
    }
  }
};
</script>
<style>

</style>
