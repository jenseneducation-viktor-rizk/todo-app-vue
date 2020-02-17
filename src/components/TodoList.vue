<template>
    <div>
        <div class="input-box">
        <label for="input">Add Task</label>
        <input
          type="text"
          class="input"
          @keyup.enter="addTodo(userInput)"
          v-model="userInput"
        />
        <ul class="input-text-container">
          <span>You have {{checkIfDone}} todos left.</span>
          <TodoItem 
          v-on:removeTodoEvent="removeTodo(todo)"
          v-bind:key="todo.id" 
          v-for="todo in todos" 
          v-bind:todo="todo"
           />
            
          
        </ul>
      </div>

    </div>
</template>

<script>
import TodoItem from "./TodoItem"
export default {
    components: {TodoItem},
    data: () =>({
      userInput: "",
      
      todos: []
    }),
    computed: {
      checkIfDone() {
        let amountUndone = 0;
        if (this.todos.length > 0) {
        for (let todo of this.todos) {
            if (todo.done == false) {
              amountUndone++
            }
          }
        }
          return amountUndone;
      }
    },
    methods:{
      addTodo(userInput) {
      
        let userTask = {
        name: userInput,
        done: false
      };
        this.todos.push(userTask);
        this.userInput = "";
      },
      removeTodo(todo) {
        const todoIndex = this.todos.indexOf(todo);
        this.todos.splice(todoIndex, 1);
      }
    
    }

    
}
</script>

<style>

</style>