<template>
  <div>
  </div>
</template>
<script>
export default {
  name:'al-table-column',
  props:{
    label:{
      type:String,
      default:""
    },
    width:{
      type:[String,Number],
      default:"auto"
    },
    prop:{
      type:String,
      default:""
    }
  },
}
</script>

<style>

</style>