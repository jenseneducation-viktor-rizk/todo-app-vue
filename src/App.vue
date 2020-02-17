<template>
  <div class="root">
    <div class="container">
      <TodoList />
    </div>
  </div>
</template>
<script>
import TodoList from "./components/TodoList"

export default {
  components: {TodoList},
};
</script>
<style>
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
}

.root {
  width: 100vw;
}
.container {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: auto;
}
.input-box {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-left: auto;
  margin-right: auto;
  width: 100vw;
  height: 600px;
  background-color: gray;
}

.input {
  padding-left: 20px;
  padding-right: 20px;
  height: 30px;
  width: 200px;
  border: none;
  border-radius: 20px;
}
.input:focus {
  outline: none;
}
.input-text-container {
  flex-direction: column;
  justify-content: center;
  align-items: center; 
  /* text-align: justify; */
  padding: 20px;
  height: 30px;
  width: 500px;
}

.input-text {
  overflow: auto;
  width: 200px;

  height: auto;
}
.done {
  text-decoration: line-through;
}
.todo-item {
  display: flex;
  justify-content: space-between;
  padding: 60px;
  font-size: 1.5rem;
}
.todo-item button {
  border: none;
  height: 40px;
  width: 100px;

}
button:focus {
  outline: none;
  
}
button:hover{
  cursor: pointer;

}

.checkbox {
  cursor: pointer;
  top: 0;
  left: 0;
  height: 25px;
  width: 25px;
  background-color: #eee;
}
</style>