<!-- HTML -->
<template>
  <div class="view">
    <h1 class="title">{{title}}</h1>
    <input type="text" @keyup.enter="addData">
    <ul>
      <li v-for="item in items" 
      :key = "item.text"
      v-bind:class="{finish:item.isFineshed}"
      @click="toggleFinish(item)">
        {{item.text}}
      </li>
    </ul>
  </div>



  
</template>


<!-- JS -->
<script>
export default {
  name: "List",
  data() {
    return {
      title: "TodoList", // 標題
      items: [
        // 代辦事項
        {
          text: "今天晚上18:00跑步",
          isFineshed: true
        },
        {
          text: "今天早上10:00吃早餐",
          isFineshed: false
        }
      ]
    };
  },
  methods: {
    toggleFinish(item) {
      item.isFineshed = !item.isFineshed;
    },
    addData() {}
  }
};
</script>
<!-- CSS -->
<style>
.view {
  width: 400px;
  border: 1px solid gray;
  margin: 20px auto;
}
.view .title {
  border-bottom: 1px solid gray;
}
.view ul li {
  margin: 10px 0;
  list-style: none;
}
.finish {
  color: grey;
  text-decoration: line-through;
}
</style>
