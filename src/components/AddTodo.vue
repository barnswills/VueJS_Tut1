<template>
  <div class="entry-container">
    <input type="text" name="title" placeholder="Add Todo..." v-model="todoEntry">
    <button class="add-button" @click="$emit('add-todo', todoEntry)">Add</button>
  </div>
</template>

<script>
export default {
  name: "AddTodo",

  data() {
    return {
      todoEntry: ""
    };
  },

  methods: {
    getEntry() {
      return this.todoEntry;
    }
  }
};
</script>

<style scoped>
.entry-container {
  display: flex;
  width: 100%;
}

.add-button {
  width: 25%;
  color: white;
  background-color: black;
}

input[type="text"] {
  flex: 10;
  padding: 5px;
}

input[type="submit"] {
  flex: 2;
}
</style>
