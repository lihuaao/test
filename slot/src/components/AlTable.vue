<template>
  <div :class = "newClass">
    <slot></slot>
    <table>
      <thead>
        <tr>
          <th
          v-for ="(item,index) in column"
          :key="index"
          :width ="item.width"
          >{{item.label}}</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for = "(row,index) in data" :key="index">
          <td
          v-for = "(col,index) in column" :key="index"
          :style = "{width:col.width}"
          >{{row[col.prop]}}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'al-table',
  props:{
    data:{
      type:Array,
      default:()=>[]
    },
    stripe:{
      type:Boolean,
      default:false
    },
    border:{
      type:Boolean,
      default:false
    }
  },
  data(){
    return {
      column:[]
    }
  },
  computed:{
    newClass(){
      return {
        stripe:this.stripe,
        border:this.border
      }
    }
  },
  mounted(){
    this.column = this.$children.map(item => item.$props);
  }
};
</script>

<style lang="scss" scoped>
*{
  margin: 0;
  padding: 0;
}
.border{
  table{
    width: 100%;
    border:1px solid #000;
    td{
      border:1px solid #000;
    }
  }
}
.stripe{
  tr:nth-child(2n) {
    background-color: #eee;
  }
}
</style>