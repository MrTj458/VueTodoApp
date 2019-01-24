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
          title: "Learn Vue",
          completed: false
        },
        {
          id: 2,
          title: "Learn MongoDB",
          completed: false
        },
        {
          id: 3,
          title: "Learn JavaScript",
          completed: true
        }
      ]
    };
  },
  methods: {
    addTodo(title) {
      this.todos.push({
        id: this.todos[this.todos.length - 1].id + 1,
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
