<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png" /> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
    <!-- <HelloWorld msg="I'm BACK BABY" /> -->

    <div class="container">
      <Header
        @toggle-add-task="toggleAddTask"
        title="Task Tracker"
        :showAddTask="showAddTask"
      />
      <div v-show="showAddTask">
        <AddTask @add-task="addTask" />
      </div>
      <Tasks
        @toggle-reminder="toggleReminder"
        @delete-task="deleteTask"
        :tasks="tasks"
      />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";
import Header from "@/components/Header";
import Tasks from "@/components/Tasks";
import AddTask from "@/components/AddTask";
// import SecondPage from "@/components/SecondPage.vue";

export default {
  name: "Home",
  components: {
    // HelloWorld,
    Header,
    Tasks,
    AddTask,
    // SecondPage,
  },
  data() {
    return {
      tasks: [],
      showAddTask: false,
    };
  },
  methods: {
    toggleAddTask() {
      this.showAddTask = !this.showAddTask;
    },
    addTask(task) {
      this.tasks = [...this.tasks, task];
    },
    deleteTask(id) {
      if (confirm("Are you sure?")) {
        this.tasks = this.tasks.filter((task) => task.id !== id);
      }
    },

    toggleReminder(id) {
      this.tasks = this.tasks.map((task) =>
        task.id === id ? { ...task, reminder: !task.reminder } : task
      );
    },
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: "Doctor's Appointment",
        day: "March 1st at 11:30am",
        reminder: true,
      },
      {
        id: 2,
        text: "Meeting at School",
        day: "March 1st at 1:30pm",
        reminder: true,
      },
      {
        id: 3,
        text: "Food Shopping",
        day: "March 1st at 4:00pm",
        reminder: false,
      },
    ];
  },
};
</script>

<style>
body {
  font-family: sans-serif;
}
.container {
  color: white;
  /* background: linear-gradient(#c8d8e8, #b6d6a2); */
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  padding: 30px;
  border-radius: 5px;
  border: 2px inset steelblue;
  text-align: start;
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
  font-family: sans-serif;
  transition: all 500ms ease-in-out;
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
