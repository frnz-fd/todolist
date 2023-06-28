<template>
  <div class="container">
    <div class="todo-box">
      <h1>Farnaz Planner</h1>

      <form @submit.prevent="handleSubmit">
        <input type="text" placeholder="Add new..." v-model="todoInput" />
        <button :disabled="!todoInput">Add</button>
      </form>

      <hr />

      <div class="todo-list" v-if="todos.length">
        <todo v-for="(todo, index) in todos" 
        :todo="todo" 
        :key="todo.id" 
        @delete="handleDelete(index)" />
      </div>
      <div v-else class="empty-todo">add your first plan ^^</div>
    </div>
  </div>
</template>

<script setup>
import { reactive, ref } from "vue";
import todo from "./components/todo.vue";

const todoInput = ref("");

function handleSubmit() {
  todos.unshift({
    id: Math.random(),
    text: todoInput.value,
    isdone: false,
  });
  todoInput.value = "";
}

function handleDelete(index){
  todo.splice(index, 1)
}

const todos = reactive([]);
</script>

<style scoped>
.container {
  display: flex;
  width: 100vw;
  height: 100vh;
  background-color: rgb(180, 90, 17);
  justify-content: center;
  align-items: center;
  flex-direction: column;
  font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
  gap: 8px;
}

h1 {
  color: rgb(142, 35, 2);
  font-weight: 900;
  margin-bottom: 48px;
  text-align: center;
}

form {
  margin-bottom: 24px;
}

form input {
  width: 500px;
  font-size: 24px;
  background-color: rgb(254, 228, 205);
  padding: 8px;
  color: rgb(74, 10, 10);
  outline: none;
  border: solid 2px rgb(254, 228, 205);
  border-radius: 8px;
}

form button {
  margin-left: 8px;
  font-size: 24px;
  padding: 8px;
  border-radius: 8px;
  border: solid 2px rgb(142, 35, 2);
  background-color: rgb(142, 35, 2);
  color: white;
}

form button[disabled] {
  background-color: gray;
  border-color: gray;
  cursor: not-allowed;
  color: rgb(230, 230, 230);
}
hr {
  margin-bottom: 18px;
  display: block;
  opacity: 0.3;
}

.todo-box {
  background-color: #eeeeee;
  border-radius: 8px;
  border: solid 2px rgb(232, 198, 149);
  box-shadow: 2px 2px 20px rgb(246, 217, 180);
  padding: 36px;
}

.todo-list {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.empty-todo{
  text-align: center;
  margin-top: 2rem;
  font-size:2rem;
  color:rgb(220, 106, 75);
}
</style>
