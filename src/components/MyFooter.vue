<template>
  <el-row>
    <el-checkbox>已完成0/全部4</el-checkbox>
    <el-button type="danger" class="clear" size="small">清除全部已完成</el-button>
  </el-row>
</template>

<script>
export default {
  name: 'MyFooter',
  data(){
    return {
      name: '张三',
      age: 18
    }
  }
}
</script>
<style scoped>
  .clear{
    float: right;
  }
</style>