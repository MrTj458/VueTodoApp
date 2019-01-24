<template>
  <div class="home">
    <TodoForm v-on:add-todo="addTodo"/>
    <TodoList class="center" v-bind:todos="todos" v-on:del-todo="removeTodo"/>
  </div>
</template>

<script>
import TodoList from "../components/TodoList";
import TodoForm from "../components/TodoForm";

export default {
  name: "home",
  components: {
    TodoList,
    TodoForm
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Todo 1",
          completed: false
        },
        {
          id: 2,
          title: "Todo 2",
          completed: false
        },
        {
          id: 3,
          title: "Todo 3",
          completed: true
        }
      ]
    };
  },
  methods: {
    addTodo(title) {
      this.todos.push({
        id: this.todos.length === 0 ? 1 : this.todos[this.todos.length - 1].id,
        title: title,
        completed: false
      });
    },
    removeTodo(id) {
      this.todos = this.todos.filter(t => t.id !== id);
    }
  }
};
</script>

<style>
.home {
  text-align: center;
}
</style>
