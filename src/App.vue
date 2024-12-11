<template>
  <div id="app">
    <h1>To-Do List</h1>
    <TodoInput @add-todo="addTodo" />
    <ul>
      <TodoItem
        v-for="(todo, index) in todos"
        :key="index"
        :todo="todo"
        @remove-todo="removeTodo(index)"
      />
    </ul>
  </div>
</template>

<script>
import TodoInput from './components/TodoInput.vue';
import TodoItem from './components/TodoItem.vue';

export default {
  components: {
    TodoInput,
    TodoItem,
  },
  data() {
    return {
      todos: [], // เก็บรายการ To-Do
    };
  },
  methods: {
    addTodo(todoText) {
      this.todos.push(todoText); // เพิ่มรายการใหม่
    },
    removeTodo(index) {
      this.todos.splice(index, 1); // ลบรายการตาม index
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
