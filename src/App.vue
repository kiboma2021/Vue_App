<script setup>
    import { ref } from 'vue';

    const name = ref("Ben Kiboma");
    const age = ref(25);
    const status = ref("active");
    const tasks = ref(['wash utensils', 'Read novel', 'Go shopping', 'Go skating']);
    const newTask = ref('');

    function toggleStatus(){
      if(status.value === "active"){
        status.value = "pending"
      } else if(status.value === "pending"){
        status.value = "inactive"
      } else {
        status.value = "active"
      }
    }

    function addTask() {
      if(newTask.value !== ""){
        tasks.value.push(newTask.value);
        newTask.value = "";
      }
    }

    function deleteTask(index) {
      tasks.value.splice(index,1);
    }

</script>

<template>
<h1>Hello {{name}}. You are {{age}} years old and your status is {{status}}</h1>
<button @click="toggleStatus">Toggle Status</button>

<p>Below are the tasks that you need to complete:</p>
<ul v-for="(task,index) in tasks" v-bind:key="task">
  <li>
    <span>{{task}} </span>
    <button @click="deleteTask(index)">X</button>
  </li>
</ul>

<hr>

<form @submit.prevent="addTask">
  <label for="newTask">New Task</label>
  <input type="text" id="newTask" name="newTask" v-model="newTask"  >
  <button type="submit">Submit</button>
</form>

</template>
