<template>
  <div class="btn">
    <p @mouseover="move" @mouseout="out">
      {{ msg }}
    </p>
    <ul :style="styleObject">
      <li v-for="(item, index) in list" :key="index">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Dropdown",
  data() {
    return {
      msg: "滑过",
      flag: false,
      styleObject: {
        height: "0px",
      },
      list: ["苹果", "橘子", "香蕉", "葡萄"],
    };
  },
  methods: {
    move() {
      this.styleObject.height = "80px";
    },
    out() {
      this.styleObject.height = "0px";
    },
  },
};
</script>

<style lang="scss" scoped>
* {
  margin: 0;
  padding: 0;
  list-style: none;
}
.btn {
  width: 100px;
  p {
    text-align: center;
    padding: 6px;
    border: 1px solid skyblue;
  }
  ul {
    text-align: center;
    height: 0px;
    overflow: hidden;
    list-style: none;
    transition: height 1s linear;
  }
}
</style>