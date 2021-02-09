<template>
    <div>
        <button @click="onClickDeleteAll">Delete all Todo</button>
    </div>
</template>
<script>
export default {
    name: 'DeleteAllTodo',
    methods: {
        onClickDeleteAll() {
            this.$emit('onDeleteAll')
        }
    },
}
</script>
