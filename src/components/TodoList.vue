<template>
    <div>
        <p> Todo List </p>
        <ul>
            <Todo v-for="todo in todos" 
            :key="todo.id" 
            :todo="todo" 
            @onDeleteHandler="onDelete" 
            @onFinishHandler="onFinish" />
        </ul>    
    </div>
</template>
<script>
import Todo from './Todo'

export default {
    name: 'TodoList', 
    components: {
        Todo
    },
    props: {
        todos: Array
    },
    methods: {
        onDelete(id) {
            this.$emit('onDelete', id)
        },
        onFinish(id) {
            this.$emit('onFinish', id)
        }
    },
}
</script>
<style lang="">
    
</style>