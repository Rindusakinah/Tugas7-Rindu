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

.container {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  background: linear-gradient(to bottom right, #2e3192, #1bffff); /* Example gradient */
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.2);
  border-radius: 16px;
  text-align: center;
  transition: all 0.3s ease-in-out;
}

.container:hover {
  box-shadow: 0 12px 36px rgba(0, 0, 0, 0.3);
}


.header {
  background-color: #28b487; 
  padding: 20px;
  border-radius: 16px 16px 0 0;
}

.header h1 {
  color: #fff;
  margin: 0;
  font-size: 2.5rem;
  font-weight: bold;
}


main {
  padding: 20px;
}


form, ul {
  background: #fff;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  margin-bottom: 20px;
}


input[type="text"] {
  width: calc(100% - 40px);
  padding: 12px;
  border: 1px solid #ddd;
  border-radius: 8px;
  margin-right: 10px;
  font-size: 1rem;
}

button {
  padding: 12px 24px;
  border: none;
  background-color: #28b487; 
  color: #fff;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #24a77e; /* Example color */
}


li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 0;
  border-bottom: 1px solid #eee;
}

li:last-child {
  border-bottom: none;
}


li span {
  flex-grow: 1;
  text-align: left;
}

li button {
  background-color: #ff4d4d;
  margin-left: 10px;
  border-radius: 8px;
}

li button:hover {
  background-color: #ff3333;
}
</style>
