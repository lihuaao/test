<template>
  <div id="app">
    <h2>tab表单</h2>
    <al-table
      :data="tableData"
      stripe
      border
      style="width: 100%">
      <al-table-column
        prop="date"
        label="日期"
        width="180px">
      </al-table-column>
      <al-table-column
        prop="name"
        label="姓名"
        width="180px">
      </al-table-column>
      <al-table-column
        prop="address"
        label="地址">
      </al-table-column>
    </al-table>
    <h2>警告框</h2>
    <message-box>
      <h4>这是一段插槽内容</h4>
    </message-box>
    <h2>按钮点击两种状态</h2>
    <notice />
    <h2>折叠面板</h2>
    <collapse />
    <h2>下拉菜单</h2>
    <dropdown />
    <h2>排序</h2>
    <timeline />
    
  </div>
</template>

<script>
import Hello from './components/HelloWorld.vue'
import AlTable from './components/AlTable'
import AlTableColumn from './components/AlTableColumn'
import Notice from './components/notice.vue';
import collapse from './components/collapse.vue'
import Dropdown from './components/Dropdown.vue';
import Timeline from './components/Timeline.vue';
import MessageBox from './components/MessageBox.vue';
export default {
  name: "App",
  data() {
    return {
      tableData: [
        {
          date: "2016-05-02",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1518 弄",
        },
        {
          date: "2016-05-04",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1517 弄",
        },
        {
          date: "2016-05-01",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1519 弄",
        },
        {
          date: "2016-05-03",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1516 弄",
        },
      ],
    };
  },
  components: {
    Hello,
    AlTable,
    AlTableColumn,
    Notice,
    collapse,
    Dropdown,
    Timeline,
    MessageBox
  },
};
</script>

<style lang="scss">
// *{
//   margin: 0;
//   padding: 0;
//   list-style: none;
//   text-decoration: none;
// }
</style>
