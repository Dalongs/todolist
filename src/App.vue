<template>
  <div>
    <MyHeader :addThings="addThings"></MyHeader>
    <MyList :todoList="todoList" :checkTodos="checkTodos"></MyList>
    <MyFooter></MyFooter>
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
    addThings(value){
      this.todoList.unshift(value);
    },
    checkTodos(id){
      console.log('父组件的id', id);
      this.todoList.forEach(item => {
        console.log(item);
        if (item.id === id) {
          item.done = !item.done;
        }
      })
    }
  }
}
</script>