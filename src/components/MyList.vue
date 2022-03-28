<template>
  <div class="list">
    <MyItem :todoList="todoList" :checkTodos="checkTodos" :deleteTodos="deleteTodos"/>
  </div>
</template>

<script>
import MyItem from './MyItem.vue';
export default {
  name: 'MyList',
  components: {
    MyItem
  },
  methods: {
    
  },
  props: ['todoList', 'checkTodos', 'deleteTodos']
}
</script>
<style scoped>
  .list{
    margin: 20px;
  }
</style>