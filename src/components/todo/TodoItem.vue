<template>
  <li>
    <label>
      <input type="checkbox" :checked="todo.done" @change="checkTodo(todo.id)"/>
      <span>{{ todo.text }}</span>
    </label>
    <button class="btn btn-danger" @click="delTodo(todo.id)">删除</button>
  </li>
</template>

<script>
export default {
  name: "TodoItem",
  props: ['todo', 'checkHandler', 'delHandler'],
  methods: {
    checkTodo(id) {
      this.checkHandler(id);
    },
    delTodo(id) {
      this.delHandler(id);
    },
  }
}
</script>

<style scoped>

</style>