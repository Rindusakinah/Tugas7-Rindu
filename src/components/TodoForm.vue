<!-- src/components/TodoForm.vue -->
<template>
  <div class="todo-form">
    <input v-model="newTodo" @keyup.enter="addTodo" placeholder="Tambahkan List" />
    <button class="add-button" @click="addTodo">Add</button>
  </div>
</template>

<script>
import { ref } from 'vue';
import { useTodoStore } from '../stores/todoStore';

export default {
  setup() {
    const todoStore = useTodoStore();
    const newTodo = ref('');

    const addTodo = () => {
      if (newTodo.value.trim() !== '') {
        todoStore.addTodo({
          id: Date.now(),
          text: newTodo.value,
          completed: false,
        });
        newTodo.value = '';
      }
    };

    return {
      newTodo,
      addTodo,
    };
  },
};
</script>

<style scoped>
.todo-form {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 20px;
  background: #ffffff;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease-in-out;
}

.todo-form:hover {
  box-shadow: 0 6px 18px rgba(0, 0, 0, 0.2);
}

.todo-form input {
  padding: 12px 15px;
  font-size: 1rem;
  border: 2px solid #ddd;
  border-radius: 8px;
  flex-grow: 1;
  margin-right: 10px;
  transition: border-color 0.3s;
}

.todo-form input:focus {
  border-color: #4CAF50;
  outline: none;
}

.add-button {
  padding: 12px 20px;
  font-size: 1rem;
  background: #4CAF50;
  color: white;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: background 0.3s, transform 0.3s;
}

.add-button:hover {
  background: #45a049;
  transform: scale(1.05);
}
</style>
