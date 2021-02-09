<template>
    <li>
        <span :class="{done: todo.finished}">{{todo.todoDescription}}</span>
        <button @click="onClickFinishHandler">{{!todo.finished? 'Finish': 'Resume'}}</button>
        <button @click="onClickDeleteHandler">Delete</button>
    </li>
</template>
<script>
export default {
    props: {
        todo: Object
    }, methods: {
        onClickDeleteHandler() {
            this.$emit('onDeleteHandler', this.todo.id)
        },
        onClickFinishHandler() {
            this.$emit('onFinishHandler', this.todo.id)
        }
    },
}
</script>
<style lang="css">
    .done {
        text-decoration:line-through;
    }
    
</style>