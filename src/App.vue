<template>
  <div id="app">
    <div class="todolist-container">
      <Header></Header>
      <AddTodo v-on:add-todo="addTodo"></AddTodo>
      <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"></Todos>
    </div>
  </div>
</template>

<script>
import Todos from "./components/Todos";
import Header from "./components/layout/Header";
import AddTodo from "./components/AddTodo";

export default {
  name: "App",
  components: {
    Todos,
    Header,
    AddTodo
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Todo One",
          completed: true
        },
        {
          id: 2,
          title: "Todo two",
          completed: true
        },
        {
          id: 3,
          title: "Todo three",
          completed: false
        }
      ]
    };
  },
  methods: {
    test() {
      alert("test");
    },
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(todoString) {
      //console.log("lets add a todo fam");

      const newId = this.todos.length + 1;

      this.todos.push({
        id: newId,
        title: todoString,
        completed: false
      });

      console.log(this.todos);
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.todolist-container {
  width: 65%;
  margin: 15px;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: #666;
}
</style>
