<template>
  <div>
    <div v-for="item in todoList" :key="item.id">
      <div class="list-item">
        <div>
          <!-- <el-checkbox :checked='item.done' @change="handleCheck(item.id)"> -->
          <el-checkbox v-model='item.done'>
            {{item.name}}
          </el-checkbox>
        </div>
        <div class="delete">
          <el-button type="danger" size="mini" @click="handleDelete(item.id)">删除</el-button>
        </div>
      </div>
    </div>
  </div>
  
</template>

<script>
export default {
  name: 'MyItem',
  data(){
    return {
      deletebtn: true
    }
  },
  props: ['todoList', 'checkTodos', 'deleteTodos'],
  methods: {
    handleCheck(id){
      this.checkTodos(id);
    },
    handleDelete(id){
      this.deleteTodos(id);
    }
  }
}
</script>
<style scoped>
  .list-item{
    height: 80px;
    border-bottom: 1px solid #eee;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 15px;
  }
  .delete{
    text-align: right;
    display: none;
  }
  .list-item:hover .delete{
    display: block;
    /* background-color: #ddd; */
  }
  .list-item:hover{
    background-color: #eee;
  }
</style>