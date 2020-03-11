<template>
<li>
    <input type="checkbox" v-model="todo.done">
    <p v-if="!editMode">{{todo.content}}</p>
    <input v-else type="text" v-model="todo.content">
    <button v-on:click="emitRemove">Delete</button>
    <button v-on:click="editMode = !editMode"> {{editMode ? 'Show' : 'Edit'}} </button>
</li>
</template>
<script>
export default {
    props: {
        todo: Object
    },
    data: function(){return{
        editMode: false,
    }},
    
    methods: {
        emitRemove(){
            this.$emit('remove')
        }
        
    }
}
</script>

<style scoped>
li{
    background-color: rgb(150,150,150);
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 0.1rem 0;
}
input{
    padding: 1rem;
    font-size: 1rem;
    text-align: center;
    box-sizing: border-box;
    border: 0;
}
p, input{
    flex-grow: 2;
    word-break:break-all;
}

button{
    border: 0;
    margin: 0.25rem;
    padding: 0.25rem;
    text-transform: uppercase;
    font-weight: 800;
}
</style>