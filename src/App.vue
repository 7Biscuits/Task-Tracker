<template>
  <div class="container">
    <Header title="Task Tracker" />
    <Tasks @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks="tasks" />
  </div>
</template>

<script>

import Header from './components/Header'
import Tasks from './components/Tasks'

export default {
  name: 'App',
  components: {
    Header,
    Tasks,
  },
  data() {
    return {
      tasks: [],
    }
  },
  methods: {
    deleteTask(id) {
      if (confirm('Are you sure you want to delete this task?')) this.tasks = this.tasks.filter(task => task.id !== id)
    },
    toggleReminder(id) {
      let myTask = this.tasks = this.tasks.filter(task => task.id)
      myTask[id-1].reminder = !myTask[id-1].reminder
    },
  },
  created() {
    this.tasks = [
      {
        id: 1,
        title: 'Task 1',
        description: 'Task 1 Description',
        day: 'day 1',
        reminder: true,
      }, 
      {
        id: 2,
        title: 'Task 2',
        description: 'Task 2 Description',
        day: 'day 2',
        reminder: true,
      },
      {
        id: 3,
        title: 'Task 3',
        description: 'Task 3 Description',
        day: 'day 3',
        reminder: true,
      }
    ]
  },
}

</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  body {
    font-family: 'Poppins', sans-serif;
  }
  .container {
    max-width: 500px;
    margin: 30px auto;
    overflow: auto;
    min-height: 300px;
    border: 1px solid steelblue;
    padding: 30px;
    border-radius: 5px;
  }
  .btn {
    display: inline-block;
    background: #000;
    color: #fff;
    border: none;
    padding: 10px 20px;
    margin: 5px;
    border-radius: 5px;
    cursor: pointer;
    text-decoration: none;
    font-size: 15px;
    font-family: inherit;
  }
  .btn:focus {
    outline: none;
  }
  .btn:active {
    transform: scale(0.98);
  }
  .btn-block {
    display: block;
    width: 100%;
  }
</style>
