<template>
  <div id="app">
    <HeaderView></HeaderView>
    <img width="25%" src="./assets/logo.png">
    <Listview/>
  </div>
</template>

<script>
import Listview from "./components/List";
import HeaderView from "./components/Header";

export default {
  name: "App",
  components: {
    Listview,
    HeaderView
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
