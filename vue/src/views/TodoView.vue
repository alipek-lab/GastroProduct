<template>
  <TodoList />
</template>

<script>
import TodoList from "../components/todo/TodoListCustomer";

export default {
  components: {
    TodoList,
  },
  name: "TodoView",
  created() {
    this.$store.dispatch("todoStore/fetchTodos");
  },
};
</script>

<style></style>
