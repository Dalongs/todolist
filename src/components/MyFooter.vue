<template>
  <el-row>
    <el-checkbox >已完成{{todoTotal}}/全部{{todoList.length}}</el-checkbox>
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
  },
  props: ['todoList'],
  computed:{
    todoTotal(){
      return this.todoList.reduce((pre, current) => {
        return pre + (current.done ? 1 : 0);
      }, 0)
    }
  }
}
</script>
<style scoped>
  .clear{
    float: right;
  }
</style>