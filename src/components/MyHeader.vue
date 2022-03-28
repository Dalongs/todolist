<template>
  <div>
    <el-input placeholder="请输入内容,按回车键新增"  v-model="title" @change="inputtodos"></el-input>
  </div>
</template>

<script>
import { nanoid } from 'nanoid';
export default {
  name: 'MyHeader',
  data(){
    return {
      title: ''
    }
  },
  methods: {
    inputtodos(){
      this.addThings({
        id: nanoid(),
        name: this.title,
        done: false
      });
      this.title = ''
    }
  },
  props: ['addThings']
}
</script>
<style>
</style>