<template>
  <el-row>
    <el-checkbox v-model="checkAll">已完成{{todoTotal}}/全部{{total}}</el-checkbox>
    <el-button type="danger" class="clear" size="small" @click="clearAll">清除全部已完成</el-button>
  </el-row>
</template>

<script>
export default {
  name: 'MyFooter',
  props: ['todoList', 'checkAllTodo', 'deleteAllTodo'],
  computed:{
    total(){
      return this.todoList.length
    },
    todoTotal(){
      return this.todoList.reduce((pre, current) => {
        return pre + (current.done ? 1 : 0);
      }, 0)
    },
    checkAll:{
      get(){
        return this.total === this.todoTotal && this.todoTotal > 0;
      },
      set(value){
        this.checkAllTodo(value);
      }
    }
  },
  methods: {
    clearAll(){
      this.deleteAllTodo();
    }
  }
}
</script>
<style scoped>
  .clear{
    float: right;
  }
</style>