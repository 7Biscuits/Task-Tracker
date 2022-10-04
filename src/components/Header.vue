<template>
    <header>
        <h1>{{ title }}</h1>
        <Button @click="$emit('toggle-showAddTask')" text="Add Task" color="green" />
    </header>
</template>

<script>

    import Button from './Button'

    export default {
        name: 'Header',
        props: {
            title: String,
        },
        components: {
            Button,
        },   
    }
</script>

<style scoped>
    header {
        display: flex;
        justify-content: space-between;
        align-self: center;
        margin-bottom: 20px;
    }
</style>