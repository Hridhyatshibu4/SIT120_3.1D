<template>
  <div class="todo-list">
    <h2>Goals and Achievements</h2>

    <!-- To-Do Tasks -->
    <div class="task-list">
      <h3>To Do</h3>
      <ul>
        <li v-for="(task, index) in filteredTasks('To Do')" :key="index">
          {{ task.text }}
          <button @click="deleteTask(index)">Delete</button>
        </li>
      </ul>
      <input v-model="newTask.text" @keyup.enter="addTask('To Do')" placeholder="Add a new task">
      <button @click="addTask('To Do')">Add Task</button>
    </div>

    <!-- In Progress Tasks -->
    <div class="task-list">
      <h3>In Progress</h3>
      <ul>
        <li v-for="(task, index) in filteredTasks('In Progress')" :key="index">
          {{ task.text }}
          <button @click="deleteTask(index)">Delete</button>
        </li>
      </ul>
      <input v-model="newTask.text" @keyup.enter="addTask('In Progress')" placeholder="Add a new task">
      <button @click="addTask('In Progress')">Add Task</button>
    </div>

    <!-- Completed Tasks -->
    <div class="task-list">
      <h3>Completed</h3>
      <ul>
        <li v-for="(task, index) in filteredTasks('Completed')" :key="index">
          {{ task.text }}
          <button @click="deleteTask(index)">Delete</button>
        </li>
      </ul>
      <input v-model="newTask.text" @keyup.enter="addTask('Completed')" placeholder="Add a new task">
      <button @click="addTask('Completed')">Add Task</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'GoalsAchievements',
  data() {
    return {
      newTask: {
        text: '',
        status: 'To Do'
      },
      tasks: []
    };
  },
  methods: {
    addTask(taskStatus) {
      if (this.newTask.text.trim() !== '') {
        this.tasks.push({ text: this.newTask.text, status: taskStatus, completed: false });
        this.newTask.text = '';
      }
    },
    deleteTask(index) {
      this.tasks.splice(index, 1);
    },
    filteredTasks(status) {
      return this.tasks.filter(task => task.status === status);
    }
  }
};
</script>

<style scoped>
/* Add your CSS styles for goals and achievements here */
</style>
