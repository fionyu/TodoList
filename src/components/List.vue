<template>
  <div class="view">
    <div class="container">
      <ul class="list-group">
        <li v-for="item in items" 
        :key = "item.text"
        v-bind:class="{'finish':item.isFineshed}"
        @click="toggleFinish(item)">
          {{item.text}}
        </li>
      </ul>
    </div>
  </div>
</template>


<!-- JS -->
<script>
export default {
  name: "List",
  data() {
    return {
      newStr: "",
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
    }
    // getStr2Items() {
    //   this.$bus.$on("getStr", data => {
    //     this.items.push({
    //       text: data,
    //       isFineshed: false
    //     });
    //   });
    // }
  }
  // mounted() {
  //   this.getStr2Items();
  // }
};
</script>

<style>
.view {
  width: 400px;
  margin: 20px auto;
}
.view .title {
  border-bottom: 1px solid gray;
}
.view ul {
  /* 讓列表前面的小點消失 */
  padding: 0;
  margin: 0;
}
.view ul li {
  /* 列表樣式 */
  /* margin: 10px 0; */
  cursor: pointer;
  padding: 12px 8px 12px 40px;
  background: #eee;
  font-size: 18px;
  transition: 0.2s;

  /* 讓列表的文字不能被反白 */
  -webkit-user-select: none;
  -moz-uer-select: none;
  -moz-user-select: none;
  user-select: none;
}
.view ul li:nth-child(odd) {
  /* 讓列表單數列顏色改變(條紋效果) */
  background: #f9f9f9;
}
.view ul li:hover {
  background: #ddd;
}
.finish {
  color: grey;
  text-decoration: line-through;
}
</style>
