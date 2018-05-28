<template>
  <div id="app">
    <HeaderView :msg="title"></HeaderView>
    <img width="25%" src="./assets/logo.png">
    <ListView @myMsg="getData"></ListView>
  </div>
</template>

<script>
// import components
import ListView from "./components/List";
import HeaderView from "./components/Header";

export default {
  name: "App",
  // register components
  components: {
    ListView,
    HeaderView
  },
  data() {
    return {
      title: "TodoList"
    };
  },
  methods: {
    getData(msg) {
      console.log("dad is here" + msg);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
