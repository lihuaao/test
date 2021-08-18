<template>
  <div class="box">
    <div class="top">
      <h2>排序</h2>
      <label for="">倒序<input type="radio" 
			:checked = "checked1"
			@click= "click"
			/></label>
      <label for="">正序<input type="radio" 
			:checked = "checked2"
			@click= "click1"
			/></label>
    </div>
    <div class="data">
      <div v-for="(item, index) in activities" :key="index">
        <h4>{{ item.content }}</h4>
        <p>{{ item.timestamp }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Timeline",
  data() {
    return {
      activities: [
        {
          content: "活动按期开始",
          timestamp: "2018-04-15",
        },
        {
          content: "通过审核",
          timestamp: "2018-04-13",
        },
        {
          content: "创建成功",
          timestamp: "2018-04-11",
        },
      ],
			checked2:false,
			checked1:true
    };
  },
	methods:{
		click(){
			this.checked1 = true,
			this.checked2 = false
			this.activities = this.activities.reverse()
		},
		click1(){
			this.checked1 = false,
			this.checked2 = true
			this.activities = this.activities.reverse()
		}
	}
};
</script>

<style lang="scss" scoped>
.box {
  .top {
    width: 200px;
    display: flex;
    justify-content: space-around;
    align-items: center;
    h2 {
      font-size: 14px;
    }
  }
}
</style>