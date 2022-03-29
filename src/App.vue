<template>
  <div>
    <MyHeader :addThings="addThings"></MyHeader>
    <MyList :todoList="todoList" :checkTodos="checkTodos" :deleteTodos="deleteTodos"></MyList>
    <MyFooter :todoList="todoList" :checkAllTodo="checkAllTodo" :deleteAllTodo="deleteAllTodo"></MyFooter>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import MyList from './components/MyList.vue'
import MyFooter from './components/MyFooter.vue'
export default {
  name: 'App',
  components: {
    MyHeader,
    MyList,
    MyFooter
  },
  data() {
    return {
      todoList: JSON.parse(localStorage.getItem('todoList')) || []
    }
  },
  methods: {
    //添加一项todo
    addThings(value){
      this.todoList.unshift(value);
    },
    //选中一项todo
    checkTodos(id){
      this.todoList.forEach(item => {
        if (item.id === id) {
          item.done = !item.done;
        }
      })
    },
    //删除一项todo
    deleteTodos(id){
      this.todoList = this.todoList.filter(item => item.id != id );
    },
    //全选todo
    checkAllTodo(done){
      this.todoList.forEach((item) => {
        item.done = done;
      })
    },
    //清楚所有已完成
    deleteAllTodo(){
      this.todoList = this.todoList.filter( item => !item.done )
    }
  },
  watch: {
      todoList: {
        deep: true,
        handler(value){
            localStorage.setItem('todoList', JSON.stringify(value))
        }
      }
  }
}
</script>