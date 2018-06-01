<template>
  <div class="header">
    <h2>{{msg}}</h2> 
    <input v-model="newStr" type="text" @keyup.enter="addData" placeholder="What do you want to do?">
  </div>
</template>
<script>
export default {
  data() {
    return {
      newStr: ""
    };
  },
  //父組件傳參數給子組件
  props: {
    // 自定義屬性
    msg: {
      type: String,
      default: "Todo List"
    }
  },
  methods: {
    addData() {
      this.$bus.$emit("getStr", "sssss");
      this.newStr = "";
    }
  }
};
</script>
<style>
h2 {
  margin: 5px;
}
.header {
  background-color: #8fbc8f;
  padding: 30px 40px;
  color: white;
  text-align: center;
}
.header:after {
  content: "";
  display: table;
  clear: both;
}
input {
  border: none;
  width: 75%;
  padding: 10px;
  /* float: center; */
  font-size: 16px;
  height: 41px;
}
</style>
