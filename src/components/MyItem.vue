<template>
  <div>
    <div v-for="item in todoList" :key="item.id">
      <div class="list-item">
        <div>
          <el-checkbox :checked='item.done' @change="handleCheck(item.id)">
            {{item.name}}
          </el-checkbox>
        </div>
        <div class="delete">
          <el-button type="danger" size="mini">删除</el-button>
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
  props: ['todoList', 'checkTodos'],
  methods: {
    handleCheck(id){
      console.log(id);
      this.checkTodos(id);
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

  }
  .delete{
    text-align: right;
    display: none;
  }
  .list-item:hover .delete{
    display: block;
    /* background-color: #ddd; */
  }
</style>