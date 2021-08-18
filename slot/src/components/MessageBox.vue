<template>
  <div class="wra">
    <a href="#" @click="click" :flag="flag">点我打开警示框</a>
    <div class="box" v-if="flag == true">
      <div class="content" :style="styleHeight">
        <div>
          <p>标题内容</p>
          <span @click="remo">X</span>
        </div>
        <div>
          <slot>这是默认内容</slot>
        </div>
        <div>
          <button @click="remo">取消</button>
          <button @click="remo">确定</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      flag: false,
      styleHeight: {
        height: "00px",
      },
    };
  },
  methods: {
    click() {
      this.flag = true;
      this.styleHeight.height = "300px";
    },
    remo() {
      this.flag = false;
    },
  },
};
</script>

<style lang="scss" scoped>
* {
  margin: 0;
  padding: 0;
  list-style: none;
  text-decoration: none;
}
.wra {
  .box {
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.3);
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    margin: auto;
    .content {
      padding: 10px 50px;
      box-sizing: border-box;
      min-width: 500px;
      overflow: hidden;
      transition: height 1s linear;
      background-color: #fff;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      display: flex;
      flex-direction: column;
      justify-content: space-around;
      div {
        display: flex;
        justify-content: space-between;
        button {
          font-size: 20px;
          background-color: #fff;
          outline: none;
          border: 1px solid transparent;
          cursor: pointer;
        }
        span {
          cursor: pointer;
        }
        p {
          font-size: 20px;
          font-weight: 700;
        }
      }
    }
  }
}
</style>