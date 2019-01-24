<template>
  <div class="card blue-grey darken-1" v-on:click="toggleCompleted" v-bind:title="hoverMessage">
    <div class="card-content white-text">
      <button v-on:click="$emit('del-todo', todo.id)" class="btn-small red right">x</button>
      <span class="card-title" v-bind:class="{'completed':todo.completed}">{{ todo.title }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "Todo",
  props: ["todo"],
  data() {
    return {
      hoverMessage: "Click to Toggle Completed."
    };
  },
  methods: {
    toggleCompleted() {
      this.todo.completed = !this.todo.completed;
    }
  }
};
</script>

<style scoped>
.completed {
  text-decoration: line-through;
}

div {
  cursor: pointer;
}
</style>
