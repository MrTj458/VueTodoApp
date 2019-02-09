<template>
  <form v-on:submit.prevent="addTodo">
    <input v-model="title" type="text" placeholder="Add a Todo...">
    <button class="btn green" type="submit">Submit</button>
  </form>
</template>

<script>
export default {
  name: "TodoForm",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    addTodo() {
      if (this.title !== "") {
        this.$emit("add-todo", this.title);
        this.title = "";
      }
    }
  }
};
</script>

<style scoped>
form {
  margin: 50px;
}
</style>
