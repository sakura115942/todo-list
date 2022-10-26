<template>
  <div class="todo-footer" v-show="total">
    <label>
      <input type="checkbox" v-model="isAll"/>
    </label>
    <span>
      <span>已完成{{ doneTotal }}</span> / {{ total }}
    </span>
    <button class="btn btn-danger" @click="delAllDoneTodo">清除已完成任务</button>
  </div>
</template>

<script>
export default {
  name: "TodoFooter",
  props: ["todos", "checkAllHandler", "delAllDoneHandler"],
  methods: {
    delAllDoneTodo() {
      this.delAllDoneHandler();
    },
  },
  computed: {
    total() {
      return this.todos.length
    },
    doneTotal() {
      return this.todos.filter(todo => todo.done).length
    },
    isAll: {
      get() {
        return this.total === this.doneTotal && this.total > 0
      },
      set(checked) {
        this.checkAllHandler(checked)
      }
    },
  }
}
</script>

<style scoped>

</style>