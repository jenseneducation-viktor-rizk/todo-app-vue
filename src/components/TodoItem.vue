<template>
    <div class="todo-item">
        <input 
        type="checkbox" 
        v-model="todo.done" 
        class="checkbox"/>
        <span :class="{ done: todo.done }">{{todo.name}}</span>
        <button @click="emitRemoveTodo">Remove</button>
    </div>
</template>

<script>

export default {
    data: () => ({
        
    }),
    methods: {
     emitRemoveTodo() {
        this.$emit("removeTodoEvent")
     }
   
    }, props: {
        todo: Object
    }
}
</script>
<style lang="stylus">

</style>