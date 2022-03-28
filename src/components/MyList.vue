<template>
  <div class="list">
    <MyItem :todoList="todoList"/>
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
  props: ['todoList']
}
</script>
<style scoped>
  .list{
    margin: 20px;
  }
</style>