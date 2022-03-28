<template>
  <div>
    <MyHeader></MyHeader>
    <MyList :todoList="todoList"></MyList>
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
  }
}
</script>