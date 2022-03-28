<template>
  <div class="list">
    <MyItem :todoList="todoList" :checkTodos="checkTodos"/>
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
  props: ['todoList', 'checkTodos']
}
</script>
<style scoped>
  .list{
    margin: 20px;
  }
</style>