<template>
  <div>
    <form>
      <input type="text" name="title" placeholder="Add Todo..." v-model="todoEntry">
      <input type="submit" value="Submit" class="btn" @click="$emit('add-todo', todoEntry)">
    </form>
  </div>
</template>

<script>
export default {
  name: "AddTodo",

  data() {
    return {
      todoEntry: "entry"
    };
  },

  methods: {
    getEntry() {
      return this.todoEntry;
    },
    test() { console.log("hello")}
  }
};
</script>

<style scoped>
form {
  display: flex;
}

input[type="text"] {
  flex: 10;
  padding: 5px;
}

input[type="submit"] {
  flex: 2;
}
</style>
