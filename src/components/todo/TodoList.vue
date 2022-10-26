<template>
  <ul class="todo-main">
    <TodoItem v-for="todo in todos" :todo="todo" :key="todo.id" :checkHandler="checkHandler" :delHandler="delHandler"/>
  </ul>
</template>

<script>
import TodoItem from "@/components/todo/TodoItem";

export default {
  name: "TodoList",
  components: {TodoItem},
  props: ['todos', 'checkHandler', 'delHandler'],
}
</script>

<style scoped>

</style>