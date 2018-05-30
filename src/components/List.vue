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
          isFineshed: false
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
    getStr2Items() {
      this.$bus.$on("getStr", data => {
        this.items.push({
          text: data,
          isFineshed: false
        });
      });
    }
  },
  mounted() {
    this.getStr2Items();
  }
};
</script>

<style>
.title {
  border-bottom: 1px solid gray;
}
ul {
  /* 讓列表前面的小點消失 */
  padding: 0;
  margin: 0;
}
ul li {
  /* 列表樣式 */
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
ul li:nth-child(odd) {
  /* 讓列表單數列顏色改變(條紋效果) */
  background: #f9f9f9;
}
ul li:hover {
  /* 滑鼠經過變色 */
  background: #ddd;
}
.finish {
  background: #888;
  color: #fff;
  text-decoration: line-through;
}
.finish::before {
  content: "";
  position: absolute;
  border-color: #fff;
  border-style: solid;
  /* 只有下面和右邊的線 */
  border-width: 0 2px 2px 0;
  top: 10px;
  left: 16px;
  /* 旋轉45度 */
  transform: rotate(45deg);
  height: 15px;
  width: 7px;
}
</style>
