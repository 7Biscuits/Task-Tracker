<template>
    <header>
        <h1>{{ title }}</h1>
        <Button @click="$emit('toggle-showAddTask')" :text="showAddTask ? 'Close' : 'Add Task'" :color="showAddTask ? 'DarkRed' : 'Green'" />
    </header>
</template>

<script>

    import Button from './Button'

    export default {
        name: 'Header',
        props: {
            title: String,
            showAddTask: Boolean
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