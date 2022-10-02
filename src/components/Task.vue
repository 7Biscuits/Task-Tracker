<template>
    <div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder ? 'reminder' : '', 'task']" >
        <h1>{{ task.title }}</h1>
        <h3>{{ task.description }}
            <i @click="$emit('delete-task', task.id)" class="fas fa-times"></i>
        </h3>
        <p>{{ task.day }}</p>
    </div>
</template>

<script>
    export default {
        name: 'Task',
        props: {
            task: Object,
        },
        emits: ['toggle-reminder', 'delete-task'],
    }
</script>

<style scope>
    .fas {
      color: red;
    }
    .task {
      background: #d5d3d3;
      margin: 5px;
      padding: 10px 20px;
    }
    .task.reminder {
      border-left: 5px solid green;
    }
    .task h3 {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }
    i {
        cursor: pointer;
    }
</style>