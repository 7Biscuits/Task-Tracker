<template>
    <header>
        <h1>{{ title }}</h1>
        <Button @click="onClick()" text="Add Task" color="green" />
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
        methods: {
            onClick() {
                console.log('onClick');
            }
        }        
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