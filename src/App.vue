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
      todoList: [
        {id: '001', name: '抽烟', done: true},
        {id: '002', name: '喝酒', done: false},
        {id: '003', name: '烫头', done: true}
      ]
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
  }
}
</script>