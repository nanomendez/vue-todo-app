<template>
    <div>
        <span>{{inputLabel}}</span>
        <input v-model="todoValue" type="text">
        <button @click="onClickHandler">Add new todo</button>
    </div>
</template>
<script>
export default {
    name: 'NewTodo',
    props: {
        inputLabel: String
    },
    data() {
        return {
            todoValue: ''
        }
    }, 
    methods: {
        onClickHandler() {
            this.$emit('onAddTodo', this.todoValue)
            this.todoValue = ''
        }
    } 
    
}
</script>
<style lang="">
    
</style>