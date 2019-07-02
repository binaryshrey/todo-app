<template>
  <div id="app" class="small-container">
   <h1>Todo List</h1>
   <todo-table />
  </div>
</template>

<script>
import TodoTable from './components/TodoTable.vue'

export default {
  name: 'app',
  components: {
    TodoTable
  },
}
</script>

<style>
button {
    background: #009435;
    border: 1px solid #009435;
  }

  .small-container {
    max-width: 680px;
  }
</style>
