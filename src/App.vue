<!-- src/App.vue -->
<template>
  <div id="app">
    <div class="container">
      <header class="header">
        <h1>Todo List Saya</h1>
      </header>
      <main>
        <TodoForm />
        <TodoList />
      </main>
    </div>
  </div>
</template>

<script>
import TodoForm from './components/TodoForm.vue';
import TodoList from './components/TodoList.vue';

export default {
  components: {
    TodoForm,
    TodoList,
  },
};
</script>

<style scoped>
/* Container styling */
.container {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  background: #f5f5f5;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  border-radius: 12px;
  text-align: center;
  transition: all 0.3s ease-in-out;
}

.container:hover {
  box-shadow: 0 6px 18px rgba(0, 0, 0, 0.2);
}

/* Header styling */
.header {
  background-color: #4CAF50;
  padding: 20px;
  border-radius: 12px 12px 0 0;
}

.header h1 {
  color: #fff;
  margin: 0;
  font-size: 2rem;
}

/* Main content styling */
main {
  padding: 20px;
}

/* Form and list styling */
form, ul {
  background: #fff;
  padding: 15px;
  border-radius: 8px;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
  margin-bottom: 20px;
}

/* Input and button styling */
input[type="text"] {
  width: calc(100% - 40px);
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 4px;
  margin-right: 10px;
}

button {
  padding: 10px 20px;
  border: none;
  background-color: #4CAF50;
  color: #fff;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #45a049;
}

/* List item styling */
li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 0;
  border-bottom: 1px solid #eee;
}

li:last-child {
  border-bottom: none;
}

/* List item text styling */
li span {
  flex-grow: 1;
  text-align: left;
}

li button {
  background-color: #ff4d4d;
  margin-left: 10px;
}

li button:hover {
  background-color: #ff3333;
}
</style>
