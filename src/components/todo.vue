<template>
  <div :class="['todo', {completed: todo.isDone}]">
    <div class="todo__info">
      <input type="checkbox" :checked="todo.isDone" />
      <p>{{ todo.text }}</p>
    </div>
    <div class="todo__actions">
      <button>❌</button>
    </div>
  </div>
</template>

<script setup>
defineProps(["todo"]);
 </script>


<style scoped>
.todo {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: rgb(201, 73, 14);
  border-radius: 4px;
  padding: 0 8px;
}

.todo:hover {
  background-color: rgb(215, 154, 12);
}

.todo.completed {
  opacity: 0.4;
}

.todo.completed p {
  text-decoration: line-through;
}

.todo .todo__info {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 24px;
}

.todo__actions button {
  border: none;
  font-size: 18px;
  cursor: pointer;
  filter: grayscale(1);
  opacity: 0.7;
  transition: 0.2s;
  background-color: transparent;
}

.todo__actions button:hover {
  filter: grayscale(0);
  opacity: 1;
}

.todo input {
  width: 24px;
  height: 24px;
}</style>
