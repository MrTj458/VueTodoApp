<template>
  <div>
    <ul>
      <li v-for="todo in todos" v-bind:key="todo.id">
        <Todo v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)"/>
      </li>
    </ul>
  </div>
</template>

<script>
import Todo from "./Todo";

export default {
  name: "TodoList",
  props: ["todos"],
  components: {
    Todo
  }
};
</script>
