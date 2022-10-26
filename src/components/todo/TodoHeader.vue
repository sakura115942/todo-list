<template>
  <div class="todo-header">
    <input type="text" placeholder="请输入你的任务名称，按回车键确认" v-model="text" @keyup.enter="addTodo"/>
  </div>
</template>

<script>
import {nanoid} from 'nanoid'

export default {
  name: "TodoHeader",
  props: ["addHandler"],
  data() {
    return {
      text: "",
    }
  },
  methods: {
    addTodo() {
      if (!this.text) return
      const todo = {
        id: nanoid(), text: this.text, done: false
      }
      this.addHandler(todo)
      this.text = ''
    },
  },
}
</script>

<style scoped>

</style>