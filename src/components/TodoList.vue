<!-- src/components/TodoList.vue -->
<template>
  <div class="todo-list">
    <ul>
      <li v-for="todo in todos" :key="todo.id" :class="{ completed: todo.completed }">
        <span @click="toggleTodo(todo.id)">
          {{ todo.text }}
        </span>
        <button class="delete-button" @click="removeTodo(todo.id)">Delete</button>
      </li>
    </ul>
    <p>List Yang Sudah Selesai: {{ incompleteTodosCount }}</p>
  </div>
</template>

<script>
import { useTodoStore } from '../stores/todoStore';
import { computed } from 'vue';

export default {
  setup() {
    const todoStore = useTodoStore();
    const todos = computed(() => todoStore.todos);
    const incompleteTodosCount = computed(() => todoStore.incompleteTodosCount);

    const toggleTodo = (id) => {
      todoStore.toggleTodo(id);
    };

    const removeTodo = (id) => {
      todoStore.removeTodo(id);
    };

    return {
      todos,
      toggleTodo,
      removeTodo,
      incompleteTodosCount,
    };
  },
};
</script>

<style scoped>
.todo-list {
  background: linear-gradient(to bottom, #f2f2f2, #e6e6e6); /* Example gradient */
  padding: 20px;
  border-radius: 16px;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease-in-out;
}

.todo-list:hover {
  box-shadow: 0 12px 36px rgba(0, 0, 0, 0.2);
}

.todo-list ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.todo-list li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 20px;
  border-bottom: 1px solid #ccc;
  background: #fff;
  border-radius: 12px;
  margin-bottom: 10px;
  transition: background 0.3s, transform 0.3s;
}

.todo-list li:hover {
  background: #f5f5f5;
  transform: translateY(-3px);
}

.todo-list li span {
  flex-grow: 1;
  cursor: pointer;
  font-size: 1.2rem;
  color: #333;
  transition: color 0.3s;
}

.todo-list li.completed span {
  text-decoration: line-through;
  color: #888;
}

.delete-button {
  background: #ff4d4d;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 8px;
  cursor: pointer;
  font-size: 1rem;
  transition: background 0.3s;
}

.delete-button:hover {
  background: #ff3333;
}

p {
  margin-top: 20px;
  font-weight: bold;
  color: #555;
  font-size: 1.2rem;
}
</style>
