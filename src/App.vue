<template>
  <div class="container">
    <div class="todo-box">
      <h1>Farnaz Planner</h1>

      <form>
        <input type="text" placeholder="Add new..." />
        <button>Add</button>
      </form>

      <hr />

      <div class="todo-list">
        <div class="todo completed">
          <div class="todo__info">
            <input type="checkbox" checked />
            <p>Buy a new Shirt!</p>
          </div>
          <div class="todo__actions">
            <button>❌</button>
          </div>
        </div>
        <div class="todo">
          <div class="todo__info">
            <input type="checkbox" />
            <p>Buy a new book!</p>
          </div>
          <div class="todo__actions">
            <button>❌</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { reactive, ref } from "vue";
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
}
</style>
