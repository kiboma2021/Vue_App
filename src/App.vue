<script>
export default {
  data() {
    return {
      name: "Ben Kiboma",
      age: 25,
      status: "active",
      tasks: ['wash utensils', 'Read nove', 'Go shopping', 'Go skating']
    }
  }
}

</script>

<template>
<h1>Hello {{name}}. You are {{age}} years old and your status is {{status}}</h1>
<p>Below are the tasks that you need to complete:</p>
<ul v-for="task in tasks" v-bind:key="task">
  <li>{{task}}</li>
</ul>


</template>
